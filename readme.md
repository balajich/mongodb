# Run mongodb in docker container
    docker pull mongo:4.0.4
    docker run -d -p 27017-27019:27017-27019 --name mongodb mongo:4.0.4
The above command will run the container in detached mode, or in the background for us. We are also mapping the container ports with host ports so that way we can access the database from a host level application if we wanted to.
    
    docker exec -it mongodb bash
The above command will connect to our deployment named mongodb using the interactive terminal and start the bash shell.
     
     mongo
MongoDB shell client
    
    show dbs
we can see what databases exist in our instance with the following
    
    use thepolyglotdeveloper
To create a new database, we can use a multi-step process, the first being to define the database we wish to use:

We’re using the database thepolyglotdeveloper, but it doesn’t exist until we start creating collections and data. To create a collection with data, we can do something like this:
    
    db.people.save({ firstname: "Nic", lastname: "Raboy" })
    db.people.save({ firstname: "Maria", lastname: "Raboy" })

With two documents created in a new people collection in our thepolyglotdeveloper database, we can query for data using something like the following:
    
    db.people.find({ firstname: "Nic" })
