set ftp1 [new Application/FTP]
$ftp1 attach-agent $tcp1
 

#Setup a FTP Application over TCP connection
set ftp2 [new Application/FTP]
$ftp2 attach-agent $tcp2
 
 set k 0
  while { $k <12 } {
  
  set m [expr int([expr 100*rand()])]  
  
  if { $m >=50 } {
    
     $ns at [expr 70.0 + [expr $k*5]]  "$ftp1 start"
     $ns at [expr 72.2 + [expr $k*5]]  "$ftp1 stop"
 
    
  } else {
   
  
    $ns at [expr 70.0 + [expr $k*5]]  "$ftp2 start"
    $ns at [expr 72.0 + [expr $k*5]]  "$ftp2 stop"
 
  }

  set k [expr $k+1]
   
 }
   
