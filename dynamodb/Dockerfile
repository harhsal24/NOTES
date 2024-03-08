FROM amazon/dynamodb-local
WORKDIR /home/dynamodblocal
RUN mkdir ./db && chown -R 1000 ./db
CMD ["-jar","DynamoDBLocal.jar","-dbPath","./db","-sharedDb"]
VOLUME ["./db"]

# docker build -t my-dynamodb-local .
# docker run -d -p 8000:8000 --name dynamodb-container my-dynamodb-local
