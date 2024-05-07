Gatling JS - JavaScript and TypeScript demo projects
============================================

A simple showcase of JavaScript and TypeScript NPM projects using Gatling JS.

# Temporary setup, until published publicly

Login to AWS:

```shell
aws sso login
# or, with a profile:
aws sso login --profile my-profile-name
```

Export environment variables:
```shell
export AWS_CODEARTIFACT_DOMAIN="domain"
export AWS_CODEARTIFACT_REGION="region"
export AWS_CODEARTIFACT_OWNER="000000000000"

export AWS_CODEARTIFACT_AUTH_TOKEN=$(aws codeartifact get-authorization-token --domain "$AWS_CODEARTIFACT_DOMAIN" --domain-owner "$AWS_CODEARTIFACT_OWNER" --query authorizationToken --output text)
export COURSIER_REPOSITORIES="ivy2Local|central|https://$AWS_CODEARTIFACT_DOMAIN-$AWS_CODEARTIFACT_OWNER.d.codeartifact.$AWS_CODEARTIFACT_REGION.amazonaws.com/maven/previews/"
export COURSIER_CREDENTIALS="$AWS_CODEARTIFACT_DOMAIN-$AWS_CODEARTIFACT_OWNER.d.codeartifact.$AWS_CODEARTIFACT_REGION.amazonaws.com aws:$AWS_CODEARTIFACT_AUTH_TOKEN"
```

# Use demo project

```shell
cd typescript # or 'cd javascript'
npm ci
npm run start # automatically download Gatling runtime, build the project, and run the simulation
```

Other commands:
```shell
npm run format # Format code with prettier
npm run check # TypeScript project only, type check but don't build or run
npm run build # Build project but don't run
```
