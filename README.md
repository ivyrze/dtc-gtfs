# Detroit People Mover GTFS

This is a community project aiming to update the Detroit People Mover GTFS feed.

## Usage

You can make use of the dataset with the following permalinks:

- GTFS: [`https://github.com/ivyrze/dtc-gtfs/releases/latest/download/gtfs-static.zip`](https://github.com/ivyrze/dtc-gtfs/releases/latest/download/gtfs-static.zip)
- GTFS-RT: [`https://github.com/ivyrze/dtc-gtfs/raw/main/gtfs-rt/alerts.pb`](https://github.com/ivyrze/dtc-gtfs/raw/main/gtfs-rt/alerts.pb)

## Development

When updating the GTFS-RT feed, the protobuf binary needs to be re-encoded. First, be sure you have the dependency:

```
brew install protobuf
```

Then, run the following commands:

```
cd gtfs-rt
wget https://github.com/google/transit/raw/master/gtfs-realtime/proto/gtfs-realtime.proto
protoc --encode=transit_realtime.FeedMessage gtfs-realtime.proto < alerts.utf8 > alerts.pb
rm gtfs-realtime.proto
```

## License

This dataset is published in the public domain.