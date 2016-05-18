# MultiEcto

This is to highlight perhaps a bug in either mix or ecto?  In the top level mix
I have defined an alias like this:

``` elixir

  defp aliases do
    [
      "ecto.reset": [
        "ecto.drop -r ProjectOne.Repo",
        "ecto.drop -r ProjectTow.Repo",
        "ecto.create -r ProjectOne.Repo",
        "ecto.create -r ProjectTow.Repo",
      ]
    ]
  end
```

However; running this only seems to effect the first repo defined in the chain:

``` bash
> mix ecto.reset
The database for ProjectOne.Repo has been dropped.
The database for ProjectOne.Repo has been created.
```
