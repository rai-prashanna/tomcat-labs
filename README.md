# tomcat-labs

if you need to do remote debugging 
add following contents within startup.sh
  export JPDA_ADDRESS=<any-port- that you want to listen other than used port>
  export JPDA_TRANSPORT=dt_socket
  
  replace **exec "$PRGDIR"/"$EXECUTABLE" "$@"** with 
          **exec "$PRGDIR"/"$EXECUTABLE" jpda start "$@"**
          
 in eclispe side,
>create new remote debug configurations
>host: <ip>
>port: <JPDA_ADDRESS>
>CONNECTION TYPE:Standard(Socket Attach)
