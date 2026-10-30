# OhMyOpenSource! Updates

> Signed update manifests for **OhMyOpenSource!** projects, served by GitHub Pages and read by [OhMyUpdater!](https://github.com/ohmyopensource/ohmyupdater) clients.

When an OhMyOpenSource! project publishes a release, its release workflow signs an update manifest and writes it here. Installations of that project (web apps, desktop apps, servers, forks) read it to tell their users that a new version is available.

## URLs

Every project has its own folder:

```
https://ohmyopensource.github.io/updates/<component>/latest.json
https://ohmyopensource.github.io/updates/<component>/latest.json.sig
```

GitHub Pages serves these files with CORS enabled, so browsers can read them from any domain.

## Trust model

**You do not need to trust this repository.** Every `latest.json` is signed with the secret key of the project it belongs to, and clients only accept it if the signature matches the public key embedded in that project. Anyone who could modify these files still could not forge a valid manifest.

Manifests also expire, and clients reject versions older than the ones they have already seen. See the [OhMyUpdater! specification](https://github.com/ohmyopensource/ohmyupdater/blob/main/spec/manifest.md) for details.

## Maintenance

The content of `site/` is written by release automation only. Do not edit manifests by hand: any change breaks their signature, and clients will reject them.

## License

The content of this repository is released under [CC0 1.0 Universal](LICENSE).
