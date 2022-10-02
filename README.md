# Detroit People Mover GTFS

This is a community project aiming to update the Detroit People Mover GTFS feed.

## Development

When updating the GTFS-RT feed, the protobuf binary needs to be re-encoded. First, be sure you have the dependency:

```
brew install protobuf
```

Then, run the following commands:

```
cd gtfs-rt
wget https://raw.githubusercontent.com/google/transit/master/gtfs-realtime/proto/gtfs-realtime.proto
protoc --encode=transit_realtime.FeedMessage gtfs-realtime.proto < alerts.utf8 > alerts.pb
rm gtfs-realtime.proto
```

## License

This dataset is published in the public domain.