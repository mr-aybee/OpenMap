# OpenMap

A Windows desktop utility for downloading map tiles from a configurable URL template. Built with C# and Windows Forms on .NET 6.

## Getting started

Open `OpenMap.sln` in Visual Studio with the .NET desktop workload and .NET 6 SDK. Restore dependencies, build and launch the application.

1. Load a JSON array of tile coordinates, for example `[{"x": 1, "y": 2, "z": 3}]`.
2. Enter an authorized tile service URL template containing `{x}`, `{y}` and `{z}`.
3. Set the maximum parallelism within the provider's usage limits, then start the download.

Tiles are stored under `Out/<z>/<x>/<y>.png`. Existing files are skipped.

## Architecture

- `Program.cs`: Windows Forms entry point.
- `Downloader.cs`: UI orchestration, parallel downloads and progress reporting.
- `MapTile.cs`: JSON coordinate model.

## Status and usage limits

Existing desktop utility; the .NET 6 target is retained for compatibility. Current runtime behavior has not been independently tested. Only download tiles from providers that permit the intended usage, and respect attribution, rate limits and storage restrictions.
