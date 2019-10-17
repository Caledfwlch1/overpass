# this is a copy of the https://github.com/drolbr/Overpass-API.git
# Go to source!!!

# Overpass-API

fixes for using the same database directory in read-only mode:

src/template_db/dispatcher.cc:55
    socket_name = db_dir + dispatcher_share_name;
==>
    socket_name = "/tmp" + dispatcher_share_name;
    
src/template_db/dispatcher_client.cc:62
    socket.open(db_dir + dispatcher_share_name_);
==>
    socket.open("/tmp" + dispatcher_share_name_);
  
src/template_db/dispatcher_client.cc:64
    std::string socket_name = db_dir + dispatcher_share_name_;
==>
    std::string socket_name = "/tmp" + dispatcher_share_name_;
    
