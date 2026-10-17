<p align="center">
  <img src="https://raw.githubusercontent.com/Dipi-App/Dipi-App.github.io/main/public/logo.png" width="100" alt="Dipi app icon">
</p>

<h1 align="center">Dipi · دیپی</h1>

<p align="center">
  <strong>The offline workday and payment ledger for Persian-speaking workers.</strong><br>
  Track workdays, wages, expenses, and payments on a Jalali calendar.<br>
  Your records stay on your phone — no account, no backend, no connection needed.
</p>

<p align="center">
  <a href="https://github.com/Dipi-App/app/releases/latest/download/dipi.apk">
    <img src="https://img.shields.io/badge/Download_APK-latest-0D3B42?style=for-the-badge&logo=android&logoColor=F8D26A" alt="Download the latest APK">
  </a>
</p>

<p align="center">
  <a href="https://github.com/Dipi-App/app/actions/workflows/build.yml"><img src="https://github.com/Dipi-App/app/actions/workflows/build.yml/badge.svg" alt="Build and release status"></a>
  <a href="https://github.com/Dipi-App/app/releases/latest"><img src="https://img.shields.io/github/v/release/Dipi-App/app?style=flat-square&label=release&color=0D3B42" alt="Latest release"></a>
  <a href="https://github.com/Dipi-App/app"><img src="https://img.shields.io/badge/platform-Android-0D3B42?style=flat-square&logo=android&logoColor=white" alt="Android"></a>
  <a href="https://github.com/Dipi-App/app/blob/main/LICENSE"><img src="https://img.shields.io/badge/license-MIT-0D3B42?style=flat-square" alt="MIT License"></a>
</p>

<p align="center">
  <a href="https://dipi-app.github.io/"><strong>Website</strong></a> ·
  <a href="https://github.com/Dipi-App/app/releases/latest"><strong>Releases</strong></a> ·
  <a href="https://github.com/Dipi-App/app"><strong>Source</strong></a>
</p>

---

## What is Dipi?

**Dipi** (دیپی) is a free, open-source Android app for Persian-speaking workers and tradespeople. It keeps daily work, wages, expense reimbursements, and payments in one private ledger and calculates each employer's balance automatically.

The app is built around the **Jalali calendar** and a **Persian, right-to-left interface**. Each employer gets a colour and a separate account. Workdays can carry hours, place, job, wage type, and notes; payments can be wages, advances, or expense refunds. Everything you enter is stored locally, so the ledger works without an account or a connection.

The name *Dipi* comes from an Old Persian word for writing. The mark is a **D** with a cuneiform wedge cut out of it.

## Features

| | |
| --- | --- |
| **Jalali work calendar**<br>Log workdays on a Jalali month grid. Employer colours and a day summary keep each entry clear. | **Employers and accounts**<br>Give every employer a colour, phone, note, and default daily wage. Archive or delete employers as needed. |
| **Payments and settlement**<br>Record wages, advances, and expense refunds. Allocate payments to pending workdays and see the running balance for each employer. | **Statistics**<br>Choose a date range and see workday, wage, and payment totals, a monthly chart, and a per-employer breakdown. |
| **Offline by design**<br>The ledger lives in a local SQLite database. No account or backend; the only network request is the GitHub release check. | **Automatic backups**<br>A JSON backup is written to the phone every 12 hours. Manual backup and restore support merge or full replacement. |
| **Reports you can share**<br>Export a date range and selected employers as TXT, Markdown, or RTL DOCX for printing or sending. | **App lock**<br>Protect the ledger with a PIN and optional biometric unlock. |

Also included: light, dark, and system themes · Toman or Rial display · Persian digits · optional voice-read help · onboarding and in-app help · an in-app update check for new GitHub releases.

## Screenshots

| **Calendar** | **Employers** | **Payments** | **Statistics** |
| :---: | :---: | :---: | :---: |
| <a href="https://dipi-app.github.io/#screenshots"><img src="https://raw.githubusercontent.com/Dipi-App/Dipi-App.github.io/main/public/screens/1-calendar-paid-dark-540.webp" width="210" alt="Dipi Jalali work calendar"></a> | <a href="https://dipi-app.github.io/#screenshots"><img src="https://raw.githubusercontent.com/Dipi-App/Dipi-App.github.io/main/public/screens/4-employers-dark-540.webp" width="210" alt="Dipi employer list"></a> | <a href="https://dipi-app.github.io/#screenshots"><img src="https://raw.githubusercontent.com/Dipi-App/Dipi-App.github.io/main/public/screens/6-payments-dark-540.webp" width="210" alt="Dipi payment history"></a> | <a href="https://dipi-app.github.io/#screenshots"><img src="https://raw.githubusercontent.com/Dipi-App/Dipi-App.github.io/main/public/screens/8-stats-dark-540.webp" width="210" alt="Dipi statistics"></a> |
| Workdays on a Jalali grid | A separate account per employer | Wage, advance, and expense records | Monthly and per-employer totals |

More screens, in both dark and light themes, are in the [gallery on the website](https://dipi-app.github.io/#screenshots).

## Repositories

| Repository | What's inside |
| --- | --- |
| [`Dipi-App/app`](https://github.com/Dipi-App/app) | The Android app: Flutter UI, Riverpod state, Drift/SQLite storage, Jalali calendar, ledger logic, backups, exports, app lock, tests, and the signed release pipeline. |
| [`Dipi-App/Dipi-App.github.io`](https://github.com/Dipi-App/Dipi-App.github.io) | The Persian RTL product site: landing page, feature and screenshot gallery, APK download cards, installation guide, and GitHub Pages deployment. |

## Technology

| Android app | Website |
| --- | --- |
| **Flutter** and **Dart**<br>**Riverpod** for state management<br>**Drift + SQLite** for local storage<br>**WorkManager** for scheduled backups<br>**local_auth** for biometric unlock<br>**GitHub Actions** for signed releases | **React 19** and **TypeScript**<br>**Vite 8** for the build<br>**Tailwind CSS 4** for styling<br>**Biome** for linting and formatting<br>**pnpm** for package management<br>**GitHub Pages** for hosting |

Every app release is built in GitHub Actions. The workflow runs `flutter analyze` and `flutter test`, builds universal and per-ABI APKs, verifies they are signed with the release key, writes SHA-256 checksums, and publishes the GitHub Release.

## Development

Clone the repository you want to work on, then:

| Android app | Website |
| --- | --- |
| **Requires:** Flutter stable, Java 17 | **Requires:** Node.js 22, pnpm 12 |
| `flutter pub get`<br>`flutter run` | `pnpm install`<br>`pnpm dev` |

See [`app/README.md`](https://github.com/Dipi-App/app/blob/main/README.md) and [`Dipi-App.github.io/README.md`](https://github.com/Dipi-App/Dipi-App.github.io/blob/main/README.md) for full setup and checks.

## Download

The universal build uses a stable `latest/download` URL. Release builds also include per-ABI APKs (`arm64-v8a`, `armeabi-v7a`, `x86_64`), each with a SHA-256 checksum.

**[Download the latest universal APK →](https://github.com/Dipi-App/app/releases/latest/download/dipi.apk)**

> The current APK is the **worker edition**. See the [website](https://dipi-app.github.io/) for current download guidance.

| Resource | Link |
| --- | --- |
| Website | [dipi-app.github.io](https://dipi-app.github.io/) |
| Latest release | [GitHub Releases](https://github.com/Dipi-App/app/releases/latest) |
| Installation guide | [Persian guide on the website](https://dipi-app.github.io/#install) |
| Issue tracker | [Dipi-App/app/issues](https://github.com/Dipi-App/app/issues) |
| Security policy | [SECURITY.md](https://github.com/Dipi-App/app/blob/main/SECURITY.md) |
| License | [MIT](https://github.com/Dipi-App/app/blob/main/LICENSE) |

## Contributing

Dipi is open source and contributions are welcome. Read the `CONTRIBUTING.md` in the repository you want to change, use [Conventional Commits](https://www.conventionalcommits.org/), and make sure the repository's checks pass. The app repository also has a [Code of Conduct](https://github.com/Dipi-App/app/blob/main/CODE_OF_CONDUCT.md).

- **App bugs and feature requests:** [open an issue](https://github.com/Dipi-App/app/issues)
- **Website bugs and docs:** [open an issue](https://github.com/Dipi-App/Dipi-App.github.io/issues)
- **Security issues:** report them privately through [GitHub Security Advisories](https://github.com/Dipi-App/app/security/advisories/new), not in a public issue.

## License

Both the [app](https://github.com/Dipi-App/app/blob/main/LICENSE) and the [website](https://github.com/Dipi-App/Dipi-App.github.io/blob/main/LICENSE) are released under the MIT License.

---

<p align="center">
  <strong>Dipi · دیپی</strong><br>
  Made for workers. Offline by design.
</p>

<p align="center">
  <a href="https://dipi-app.github.io/">Website</a> ·
  <a href="https://github.com/Dipi-App/app">App</a> ·
  <a href="https://github.com/Dipi-App/Dipi-App.github.io">Website source</a>
</p>

<p align="center">
  Developed by <a href="https://mst-ghi.github.io/">Mostafa</a>.
</p>
