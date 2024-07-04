__spotify_script.ipynb__: several instances of this script were executed for extracting song and artist ids.

Once all successfully extracted, audio features were fetched using each song id:

  import spotipy
  from spotipy.oauth2 import SpotifyClientCredentials
  
  client_credentials_manager = SpotifyClientCredentials(client_id=CLIENT_ID, client_secret=CLIENT_SECRET)
  sp = spotipy.Spotify(client_credentials_manager=client_credentials_manager)
  
  def get_audio_features(song_ids):
      features = sp.audio_features(tracks=song_ids)
      return features
