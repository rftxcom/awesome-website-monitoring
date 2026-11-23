# Awesome Website Monitoring [![Awesome](https://awesome.re/badge.svg)](https://awesome.re) [![Security Score](https://badge.rftmedia.com/badge/rftmedia.com.svg)](https://domain.rftmedia.com)

> A curated list of tools, services, and resources for monitoring website health, uptime, performance, and security.

**🛡️ Add a security badge to your repo:** [badge.rftmedia.com](https://badge.rftmedia.com)

Whether you're a developer, DevOps engineer, or business owner, keeping your websites healthy is crucial. This list covers everything from simple uptime checks to comprehensive security monitoring.

## Contents

- [Uptime Monitoring](#uptime-monitoring)
- [Performance Monitoring](#performance-monitoring)
- [Security Monitoring](#security-monitoring)
- [SSL Certificate Monitoring](#ssl-certificate-monitoring)
- [CI/CD Integration](#cicd-integration)
- [Self-Hosted Solutions](#self-hosted-solutions)
- [Command Line Tools](#command-line-tools)
- [Browser Extensions](#browser-extensions)
- [Status Pages](#status-pages)
- [Incident Management](#incident-management)
- [Learning Resources](#learning-resources)

---

## Uptime Monitoring

*Tools that check if your website is up and alert you when it goes down.*

### Commercial Services

- [UptimeRobot](https://uptimerobot.com/) - Free tier with 50 monitors, 5-minute intervals.
- [Pingdom](https://www.pingdom.com/) - Enterprise-grade monitoring with detailed analytics.
- [Better Uptime](https://betteruptime.com/) - Modern uptime monitoring with status pages.
- [StatusCake](https://www.statuscake.com/) - Page speed, SSL, and uptime in one platform.
- [Uptime.com](https://uptime.com/) - Multi-location monitoring with RUM.
- [Site24x7](https://www.site24x7.com/) - Full-stack monitoring for websites and applications.
- [Datadog Synthetics](https://www.datadoghq.com/product/synthetic-monitoring/) - Enterprise monitoring integrated with APM.

### Developer Tools

- [RFT Site Monitor](https://tools.rftmedia.com/monitor) - Free website health checker with security audit. ⭐
- [Checkly](https://www.checklyhq.com/) - API & browser monitoring for developers.
- [Hyperping](https://hyperping.io/) - Simple, fast uptime monitoring.
- [OnlineOrNot](https://onlineornot.com/) - Uptime monitoring for Jamstack sites.

## Performance Monitoring

*Tools that measure website speed and identify bottlenecks.*

### Speed Testing

- [Google PageSpeed Insights](https://pagespeed.web.dev/) - Google's official speed analysis tool.
- [GTmetrix](https://gtmetrix.com/) - Detailed performance reports with waterfalls.
- [WebPageTest](https://www.webpagetest.org/) - Advanced testing from multiple locations.
- [Lighthouse](https://developer.chrome.com/docs/lighthouse/) - Google's auditing tool for performance, SEO, accessibility.
- [RFT Website Grader](https://tools.rftmedia.com/grader) - Free instant website score with recommendations. ⭐

### Real User Monitoring (RUM)

- [SpeedCurve](https://www.speedcurve.com/) - Synthetic + RUM with beautiful dashboards.
- [Calibre](https://calibreapp.com/) - Performance monitoring and budgets.
- [Request Metrics](https://requestmetrics.com/) - Core Web Vitals monitoring.
- [Treo](https://treo.sh/) - Page speed monitoring with Lighthouse.

## Security Monitoring

*Tools that scan for vulnerabilities and security issues.*

### Vulnerability Scanners

- [RFT Security Scanner](https://tools.rftmedia.com/security) - Free security headers audit with instant report. ⭐
- [Mozilla Observatory](https://observatory.mozilla.org/) - Security headers analysis by Mozilla.
- [Security Headers](https://securityheaders.com/) - Quick HTTP security header check.
- [Qualys SSL Labs](https://www.ssllabs.com/ssltest/) - Deep SSL/TLS analysis.
- [ImmuniWeb](https://www.immuniweb.com/websec/) - Free website security test.
- [Detectify](https://detectify.com/) - Automated security scanning.

### Security Monitoring Services

- [Snyk](https://snyk.io/) - Developer-first security platform.
- [Sucuri](https://sucuri.net/) - Website security and malware removal.
- [Wordfence](https://www.wordfence.com/) - WordPress security plugin and scanning.
- [Cloudflare](https://www.cloudflare.com/) - WAF, DDoS protection, and security.

## SSL Certificate Monitoring

*Tools that track SSL certificate expiration and issues.*

- [SSL Mate](https://sslmate.com/certspotter/) - Certificate transparency monitoring.
- [Cert Spotter](https://sslmate.com/certspotter/) - Free CT log monitoring.
- [KeyChest](https://keychest.net/) - SSL/TLS certificate monitoring.
- [Certificate Monitor](https://certificatemonitor.org/) - Free SSL expiry alerts.
- [RFT SSL Checker](https://tools.rftmedia.com/security) - Checks SSL validity and chain issues. ⭐

## CI/CD Integration

*Monitor your website as part of your deployment pipeline.*

### GitHub Actions

- [**Site Health Check Action**](https://github.com/rftxcom/site-health-check-action) - Check website health, SSL, security headers in CI/CD. ⭐ **Recommended**
- [Lighthouse CI Action](https://github.com/treosh/lighthouse-ci-action) - Run Lighthouse in GitHub Actions.
- [Pa11y CI](https://github.com/pa11y/pa11y-ci) - Accessibility testing in CI.
- [Checkly GitHub Action](https://github.com/checkly/checkly-action) - Run Checkly checks in CI.

### Usage Example

```yaml
name: Website Health Check

on:
  push:
    branches: [main]
  schedule:
    - cron: '0 */6 * * *'  # Every 6 hours

jobs:
  health-check:
    runs-on: ubuntu-latest
    steps:
      - uses: rftxcom/site-health-check-action@v1
        with:
          url: 'https://your-website.com'
          fail-on-issues: 'true'
```

### Other CI/CD Tools

- [Speedlify](https://github.com/zachleat/speedlify) - Lightweight performance monitoring for CI.
- [URLBox](https://urlbox.io/) - Screenshot and render websites in CI.

## Self-Hosted Solutions

*Run your own monitoring infrastructure.*

### Open Source

- [Uptime Kuma](https://github.com/louislam/uptime-kuma) - Self-hosted monitoring with beautiful UI. ⭐ Popular
- [SiteWatcher](https://github.com/NikKurkov/sitewatcher) - Self-hosted uptime checks, TLS and domain expiry alerts, and public status pages.
- [Statping](https://github.com/statping/statping) - Status page and monitoring.
- [Gatus](https://github.com/TwiN/gatus) - Developer-oriented health dashboard.
- [Vigil](https://github.com/valeriansaliou/vigil) - Microservices status page.
- [Monitoror](https://github.com/monitoror/monitoror) - Unified monitoring wallboard.

### Prometheus Stack

- [Blackbox Exporter](https://github.com/prometheus/blackbox_exporter) - Probing for Prometheus.
- [Grafana](https://grafana.com/) - Visualization and alerting.
- [AlertManager](https://prometheus.io/docs/alerting/latest/alertmanager/) - Alert handling.

## Command Line Tools

*Check website health from your terminal.*

### Node.js / NPM

- [**@rftmedia/site-health**](https://github.com/rftxcom/site-health-npm) - Check SSL, headers, performance from CLI. ⭐ **Recommended**
  ```bash
  npx @rftmedia/site-health example.com --json
  ```
- [lighthouse-cli](https://www.npmjs.com/package/lighthouse) - Run Lighthouse from terminal.
- [is-website-vulnerable](https://www.npmjs.com/package/is-website-vulnerable) - Check for known vulnerabilities.

### Python / PyPI

- [**site-health**](https://github.com/rftxcom/site-health-python) - Python library for website health checks. ⭐ **Recommended**
  ```bash
  pip install site-health
  site-health example.com
  ```
- [httpie](https://httpie.io/) - Human-friendly HTTP client.
- [ssl-cert-check](https://pypi.org/project/ssl-cert-check/) - SSL certificate checker.

### General Tools

- [curl](https://curl.se/) - The classic HTTP tool.
- [httpstat](https://github.com/reorx/httpstat) - curl statistics visualized.
- [hey](https://github.com/rakyll/hey) - HTTP load generator.
- [vegeta](https://github.com/tsenart/vegeta) - HTTP load testing tool.

## Browser Extensions

*Monitor websites while you browse.*

- [Wappalyzer](https://www.wappalyzer.com/) - Identify web technologies.
- [Lighthouse](https://chrome.google.com/webstore/detail/lighthouse) - Chrome's built-in audit tool.
- [BuiltWith](https://builtwith.com/) - Technology profiler.
- [Web Developer](https://chrispederick.com/work/web-developer/) - Various web dev tools.

## Status Pages

*Communicate uptime to your users.*

### Hosted Services

- [Statuspage.io](https://www.atlassian.com/software/statuspage) - Atlassian's status page solution.
- [Instatus](https://instatus.com/) - Fast, beautiful status pages.
- [Sorry](https://www.sorryapp.com/) - Status communication platform.
- [Cachet](https://cachethq.io/) - Open source status page (self-hosted).

### Service Status Checkers

- [RFT Status Hub](https://status.rftmedia.com) - Check if major services are down. ⭐
- [Downdetector](https://downdetector.com/) - Crowdsourced outage reports.
- [isitdownrightnow](https://www.isitdownrightnow.com/) - Simple status checker.

## Incident Management

*Handle outages when they happen.*

- [PagerDuty](https://www.pagerduty.com/) - Industry-standard incident management.
- [OpsGenie](https://www.atlassian.com/software/opsgenie) - Alerting and on-call management.
- [Incident.io](https://incident.io/) - Modern incident management.
- [Rootly](https://rootly.com/) - Incident response automation.

## Learning Resources

### Articles

- [Web Performance 101](https://web.dev/performance/) - Google's performance guide.
- [Security Headers](https://securityheaders.com/about/) - Understanding HTTP security headers.
- [Core Web Vitals](https://web.dev/vitals/) - Google's user experience metrics.

### Books

- *High Performance Browser Networking* - Ilya Grigorik (Free online)
- *Web Performance in Action* - Jeremy Wagner
- *Designing for Performance* - Lara Hogan

### Courses

- [Web Performance](https://frontendmasters.com/courses/web-performance/) - Frontend Masters
- [Website Optimization](https://www.udacity.com/course/website-performance-optimization--ud884) - Udacity (Free)

---

## Contributing

Contributions welcome! Read the [contribution guidelines](CONTRIBUTING.md) first.

## License

[![CC0](https://mirrors.creativecommons.org/presskit/buttons/88x31/svg/cc-zero.svg)](https://creativecommons.org/publicdomain/zero/1.0/)
