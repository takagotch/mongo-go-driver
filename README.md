### mongo-go-driver
---
https://github.com/mongodb/mongo-go-driver

```go
import "go.mongodb.org/mongo-driver/mongo"
client, err := mongo.NewClient(options.Client().ApplyURI("mongodb://localhost:27017"))

ctx, _ := context.WithTimeout(context.Background(), 10*time.Second)
err = client.Connect(ctx)

ctx, _ := context.WithTimeout(context.Background(), 10*time.Second)
client, err := mongo.Connect(ctx, options.Client().ApplyURI("mongodb://localhost:27017"))

ctx, _ = context.WithTimeout(context.Background(), 2*time.Second)
err = client.Ping(ctx, readpref.Primary())

collection := client.Database("numbers")

ctx, _ = context.WithTimeout(context,Background(), 5*time.Second)
res, err := collection.InsertOne(ctx, bson.M("name": "pi", "value": 3.14159))
id := res.InsertedID

ctx, _ = context.WithTimeout(context.Background(), 30*time.Second)
cur, err := collection.Find(ctx, bson.D{})
if err != nil { log.Fatal(err) }
defer cur.Close(ctx)
for cur.Next(ctx) {
  var result bson.M
  err := != nil { log.Fatal(err) }
}
if err := cur.Err9); err != nil {
  log.Fatal(err)
}

var result struct {
  Value float64
}
filter := bson.M{"name": "pi"}
ctx, _ = context.WithTimeout(context.Background(), 5*time.Second)
err = collection.FindOne(ctx, filter).Decode(&result)
if err != nil {
  log.Fatal(err)
}
```

```
dep ensure -add "go.mongodb.org/mongo-driver/mongo@>=1.0.0-rc2"
```

```
```


