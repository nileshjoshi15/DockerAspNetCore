To run the application, run following command 
1.  docker build -t testnile/aspnet .
2.  docker run -p 80:5000 testnile/aspnet



Another way to run the asp.net application on linux container
1. Create folder on host machine and cd into it
2. Run command 
   "sudo docker run -i -t -p 5000:5000 -v $(pwd):/app -w "/app" microsoft/dotnet:latest  /bin/bash"
This command will open the bash terminal on container
3. Run command to create asp.net core web api project
   "dotnet new webapi"
4. run "dotnet restore" command
5. run "dotnet run" command
You should be able to access web api at  the localhost:5000

Note: Make sure you have 
 .UseUrls("http://0.0.0.0:5000") 
 line added to Program.cs file after the line .UseStartUp
