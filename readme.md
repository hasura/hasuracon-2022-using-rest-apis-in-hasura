```gql
scalar Price

type Track {
  TrackId: Int!
  Name: String!
  AlbumId: Int
  AlbumTitle: String
  ArtistId: Int
  ArtistName: String
  MediaTypeId: Int!
  MediaTypeName: String!
  GenreId: Int
  GenreName: String
  Composer: String
  Milliseconds: Int!
  Bytes: Int
  UnitPrice: Price
}


type Playlist {
  Name: String
  Tracks: [Track!]!
}


type Query {
  genre: Genre
  track_by_id(id: Int!): Track
  track(limit: Int, offset: Int): [Track]
  playlist_by_id (id: Int): Playlist
  playlist(limit: Int, offset: Int): Playlist
}

type Mutation {
  create_playlist(Name: String, PlaylistTracks: [Int!]!): Playlist!
  update_playlist(PlaylistId: Int! Name: String): Playlist!
  delete_playlist(PlaylistId: Int!): Playlist!
  create_playlist_track(PlaylistId: Int! TrackId: Int!): Playlist!
  delete_playlist_track(PlaylistId: Int! TrackId: Int!): Playlist!
}

```