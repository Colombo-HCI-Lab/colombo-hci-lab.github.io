# Colombo HCI Lab — Website

Website of the **Colombo HCI Lab**, University of Colombo School of Computing (UCSC).
Live at **https://colombo-hci-lab.github.io**

## How the site works

Plain HTML + CSS + JS, no build step. All routine content lives in `data/*.json` —
you rarely need to touch HTML:

| File | Controls |
|---|---|
| `data/index.json` | Home page intro, research highlight cards, news items |
| `data/project.json` | Research page project descriptions |
| `data/publications.json` | Publications page entries |
| `data/team.json` | Team page members and sections |
| `data/contact.json` | Contact page intro |

`js/main.js` renders the shared header/footer and injects JSON content into each page.
Styling is in `css/style.css`. Photos go in `images/`, paper PDFs in `publications/`.

### Adding a news item
Edit `data/index.json` and add an object at the **top** of the `news` array:
```json
{ "date": "Jul 2026", "heading": "Something great happened", "link": "https://..." }
```

### Adding a team member
Add their photo to `images/`, then add an entry to the matching array in `data/team.json`.

### Adding a publication
Add an entry to `data/publications.json` (newest year first). Put the PDF in `publications/` if you have rights to share it.

## Previewing locally
JSON is loaded with `fetch`, so open the site through a local server (not `file://`):
```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Contributing
1. `git clone https://github.com/Colombo-HCI-Lab/colombo-hci-lab.github.io.git`
2. Create a branch: `git checkout -b your-name`
3. Make changes, commit, push, and open a pull request.
