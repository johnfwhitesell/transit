My goal here is to make an API pull script and a mapping app.  
The data is pulled from the transitscreenAPI.  It is then mapped onto a folium map.

v0.2 (Stardate 180313.8)
Right now the only points being pulled are the center of the hexes.  This isn't representative and gives weird resultsjo near anacostia park.  I am currently looking into new data sources for addresses.  DC open government has a good listing of every residence in the district but it's limited to 1000 requests at a time (and is over 300k).  If I can put together this list, randomly sampling it to select which locations to pull will give a more representative map.  (I could also add a housing density layer).

I should also clarify the way the values are made. Right now the hexagon shapes are in a geopandas dataframe along with the transitscores.  The hexes are saved to a json, which folium uses to make shapes.  The transitscores aren't assigned to the shapes, they are just within the range of them which means averaging the shapes gives the result of the only transitscore it contains.

v0.1 (Stardate 180312.6)
Did a first draft version.  The pulling is in data_frame_maker.  You need an API key from TransitScreen.
The data is saved to hex_pickle.
The map is made with mapper_from_pickle.
The mapper makes an html, I renamed that "index" so that I could make it a github page.
