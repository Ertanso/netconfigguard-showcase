# NetConfigGuard — English overview

Network configuration governance: from configuration snapshots to evidence-based findings, risk and reporting.

**0.3.0-alpha.1 · Commercial implementation remains private · Public product and engineering documentation**

NetConfigGuard versions vendor configuration snapshots, compares supported semantic objects, evaluates supported static posture rules and presents findings, control references and risk outputs with snapshot context.

## End-to-end workflow

1. Prepare deployment, tenant/admin access and local product license activation.
2. Register the device and configure an applicable collector, or use manual snapshot upload.
3. Track asynchronous collection through job records and retain raw snapshot history.
4. Compare snapshot pairs for meaningful supported changes; evaluate static posture independently on a single snapshot where implemented.
5. Review findings, compliance evaluations and change/baseline risk as distinct outputs.
6. Use reporting, PDF, audit/job visibility and configured alert channels for follow-up.
7. Apply corrections through the operator's change process and collect a new snapshot for reassessment.

Optional AI explanations, chat, report summaries and policy drafts remain advisory. Framework mappings are neither certification nor a legal compliance determination.

## Engineering and evidence

Go API/Worker, React 19/TypeScript, PostgreSQL 16, Redis 7, Docker/Compose, Helm, Prometheus and OpenTelemetry. Domain, application, vendor parsing, persistence and HTTP concerns are separated. Collection uses persisted PostgreSQL jobs and worker polling; the presence of Redis does not imply that all jobs use a Redis queue.

Go/Web/Helm/Secret scan CI passed for the alpha merge. Local evidence includes mandatory database integration, race checks, authentication smoke, linux/arm64 offline clean/repeat installation and backup/restore. No live-device L3 validation, independent penetration-test report or production pilot acceptance is recorded.

The public vendor table shows the canonical depth matrix's 33 entries. Coverage differs by vendor; previous summaries' 34 catalog count is not treated as an equivalent production-support metric.

## Detailed reading path

The full guide is currently in Turkish:

- [Product concepts](docs/product-overview.md)
- [User journey and sequence diagram](docs/user-journey.md)
- [UI page/tab guide](docs/interface-guide.md)
- [Semantic analysis, baseline risk and control boundaries](docs/analysis-pipeline.md)
- [Vendor coverage](docs/vendor-coverage.md)
- [Architecture](docs/architecture.md)
- [Authentication, offline licensing and AI](docs/security-and-ai.md)
- [Deployment and operations](docs/deployment-and-operations.md)
- [Engineering case study](docs/portfolio-case-study.md)
- [Validation and roadmap](docs/validation.md)

The [visual tour](docs/visual-tour.md) includes 18 actual browser captures using synthetic laboratory data, a [100-second silent, captioned MP4 screen tour](media/netconfigguard-laboratory-tour.mp4) and a [sample report PDF](media/netconfigguard-laboratory-report.pdf). Capture uses an alpha-based development branch with governance-view fixes, not the unchanged initial release archive. A [106-second Turkish teaser](media/netconfigguard-linkedin-teaser.tr.mp4) uses mobile-friendly 4:5 framing and burned-in subtitles, distinguishing current configuration analysis from future unified management and instant manager notification goals. A [detailed Turkish narrated product demonstration](media/netconfigguard-product-walkthrough.tr.mp4) explains each screen and its purpose; see [chapters and transcript](docs/product-walkthrough.tr.md). A [Turkish synthetic narration version](media/netconfigguard-laboratory-tour-narrated.tr.mp4) and [subtitle file](media/netconfigguard-laboratory-tour.tr.srt) are also available. The voice uses macOS Yelda text-to-speech. The video is edited from actual application screenshots, with a fixed 1080p canvas; it is not a continuous interaction recording. No hosted interactive demo is available. Contact [Ertan Soyalp](https://github.com/Ertanso) for a walkthrough or pilot discussion. Source code, deployment archives and activation material are private. All rights reserved; [LICENSE](LICENSE).
