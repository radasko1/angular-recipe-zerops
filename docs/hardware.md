# Hardware Requirements

## Minimal Requirements

**CPU:** 1 vCPU (shared)
- Static sites have minimal processing needs
- Node.js just serves pre-built files, no runtime compilation

**RAM:** 512 MB - 1 GB
- Node.js itself: ~50-100 MB base memory
- Basic web server (Express/Serve/http-server): ~20-50 MB
- OS overhead: ~200-300 MB
- Leaves comfortable headroom for traffic spikes

**Storage:** 5-10 GB
- OS: ~2-3 GB
- Node.js runtime + dependencies: ~500 MB - 1 GB
- Static assets: varies (typically 100 MB - 2 GB)
- Logs and system files: ~1-2 GB

## Real-World Considerations (Production)

- **CPU:** 1-2 vCPUs (dedicated)
- **RAM:** 1-2 GB
- **Storage:** 20 GB SSD

**Why?**
- Higher traffic
- OS updates (security patches)
- Monitoring agents (Datadog, New Relic, etc.)
- Log aggregation
- SSL/TLS termination overhead
- Container runtime if using Docker

## Better Approach

Honestly, for a static site, I'd question using Node.js at all. Consider:
- **Nginx/Apache** - Much lighter weight (~10 MB RAM vs 100+ MB)
- **CDN** (Cloudflare, CloudFront) - Better performance, DDoS protection
- **Static hosting** (Netlify, Vercel, S3+CloudFront) - Near-zero maintenance
