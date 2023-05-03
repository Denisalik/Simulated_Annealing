## Task 2
Firstly we load the data and find 30 largest cities:
```
df[df.index.isin(df['population'].nlargest(30).index)]
```
Also, we parse json for Russia's borders.

To find distance between 2 points we use: `geopy.distance.geodesic`.
Whole distance is distance between all points in salesman path.

As we need to cross between 2 cities only once,
we don't need to create graph with nodes and edges,
we can just put path order for cities how salesman should cross cities.

Method `annealing` contains implementation for SA using fixed number of iterations and cooling algorithm(it is still fixed number of iterations, but we need to calculate number of iterations based on temperature, gamma and temperature limit).
So we need to provide either `temp_limit` or `iterations`.

Method `plot_map` contains implementation for plotting map for current frame.

Method `make_animation` contains implementation make annealing,
make plots for every step and make animation from plots and return this animation.
It require fixed number of iterations, so if you want to have implementation for `temp_limit`, `iterations` should have bigger value than number of iterations calculated from `temp_limit`.

Everything else needed for algorithm and self-explanatory.

See `1000_ani.mp4` as an example of animation.