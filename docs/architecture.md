# DevTrack — Architecture

## Approved stack
- TypeScript
- Next.js App Router
- Node.js and Express REST API
- PostgreSQL
- Drizzle ORM
- Modular monolith

## Request flow
Browser
  -> Next.js pages or /api routing
  -> Express REST API
  -> Validation and session authentication
  -> Service-layer authorization and business rules
  -> Drizzle repositories
  -> PostgreSQL

## Same-origin routing
Local development:
- Next.js: port 3000
- Express: port 4000
- Browser API requests use relative URLs such as /api/projects.
- Next.js forwards /api requests to Express.

Production:
- Browser uses one public HTTPS origin.
- API requests are routed to Express.
- Database access stays server-side.

The exact routing configuration and hosting setup remain unverified.

## Security
- Store only hashes of opaque session tokens.
- Use HttpOnly, SameSite=Lax cookies.
- Enable Secure cookies over HTTPS.
- Validate Origin and implement CSRF protection.
- Keep database credentials server-side.
- Authorize every protected operation.
- Test cross-tenant isolation.

## Deferred complexity
Redis, microservices, AI, and real-time collaboration are excluded
from the MVP.
