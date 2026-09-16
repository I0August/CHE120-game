# Dana Porter Book Grab — Web Edition

A University of Waterloo CHE 120 game built with Python and Pygame. This edition is ready to run in modern web browsers through [pygbag](https://pygame-web.github.io/wiki/pygbag/).

## Controls

- Click **Start Game**, then **Next**.
- Move with `W`, `A`, `S`, and `D`.
- Press `E` when standing on a book to collect it.
- Collect all seven books as quickly as possible.

Audio starts after the first click because browsers do not permit pages to autoplay sound.

## Test locally in a browser

Python 3.11 or 3.12 is recommended.

```bash
python -m venv .venv
source .venv/bin/activate       # Windows: .venv\Scripts\activate
python -m pip install -r requirements.txt
python -m pygbag --no_opt --ume_block 0 .
```

Open <http://localhost:8000> in Chrome, Edge, or Firefox. Stop the server with `Ctrl+C`.

## Build static web files

```bash
python -m pygbag --build --no_opt --ume_block 0 .
```

The generated site is written to `build/web`. Test that directory through a local web server; opening `index.html` directly with a `file://` URL will not work reliably.

## Publish on GitHub Pages

This repository includes `.github/workflows/deploy-pages.yml`.

1. Create a GitHub repository and upload the contents of this folder. `main.py` must remain at the repository root.
2. On GitHub, open **Settings → Pages** and choose **GitHub Actions** as the source.
3. Push to `main`, or manually run **Deploy web game to GitHub Pages** from the Actions tab.
4. After the workflow finishes, the game will be available at `https://YOUR-USERNAME.github.io/YOUR-REPOSITORY/`.

Do not upload `.venv`, `__pycache__`, or a local `build` directory; the workflow recreates the web build.

## Credits

This project was created for the University of Waterloo Department of Chemical Engineering CHE 120 computer literacy and coding class.

- Clear Code. “The Ultimate Introduction to Pygame.” YouTube, 2021.
- Russ. “Tile Based Platformer Game Tutorial.” YouTube, 2020.
- “Distant Sky” by Keys of Moon, promoted by Chosic, licensed under CC BY 4.0.
- “Item Equip” sound effect from Pixabay, accessed October 27, 2024.
