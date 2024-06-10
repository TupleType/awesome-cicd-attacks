# Awesome CI/CD Attacks [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
Practical resources for offensive CI/CD security research.

## Contents

- [Techniques](#techniques)
  - [Publicly Exposed Sensitive Data](#publicly-exposed-sensitive-data)
  - [Initial Code Execution](#initial-code-execution)
  - [Post Exploitation](#post-exploitation)
  - [Defense Evasion](#defense-evasion)
- [Offensive Tools](#offensive-tools)
- [Case Studies](#case-studies)
- [Similar Projects](#similar-projects)

## Techniques
A curated list of unique and useful CI/CD attack techniques.

### Publicly Exposed Sensitive Data
- [(The) Postman Carries Lots of Secrets](https://trufflesecurity.com/blog/postman-carries-lots-of-secrets)
- [All the Small Things: Azure CLI Leakage and Problematic Usage Patterns](https://www.paloaltonetworks.com/blog/prisma-cloud/secrets-leakage-user-error-azure-cli/)
- [Beyond S3: Exposed Resources on AWS](https://duo.com/blog/beyond-s3-exposed-resources-on-aws) - Public EBS, RDS, AMI and ElasticSearch clusters exposed to the internet. 
- [CloudQuarry: Digging for secrets in public AMIs](https://securitycafe.ro/2024/05/08/aws-cloudquarry-digging-for-secrets-in-public-amis/)
- [Employee Personal GitHub Repos Expose Internal Azure and Red Hat Secrets](https://www.aquasec.com/blog/github-repos-expose-azure-and-red-hat-secrets/)
- [Fortune 500 at Risk: 250M Artifacts Exposed via Misconfigured Registries](https://www.aquasec.com/blog/250m-artifacts-exposed-via-misconfigured-registries/) - Misconfigured public registries with software artifacts containing sensitive proprietary code and secrets.
- [GitLab Secrets](https://github.com/RichardoC/gitlab-secrets) - A tool that can reveal deleted GitLab commits that potentially contain sensitive information and are not accessible via the public Git history.
- [Hidden GitHub Commits and How to Reveal Them](https://neodyme.io/en/blog/github_secrets/) - A tool that can reveal deleted GitHub commits that potentially contain sensitive information and are not accessible via the public Git history.
- [Holes in Your Bitbucket: Why Your CI/CD Pipeline Is Leaking Secrets](https://cloud.google.com/blog/topics/threat-intelligence/bitbucket-pipeline-leaking-secrets)
- [Publicly Exposed AWS Document DB Snapshots](https://ramimac.me/exposed-docdb)
- [Thousands of images on Docker Hub leak auth secrets, private keys](https://www.bleepingcomputer.com/news/security/thousands-of-images-on-docker-hub-leak-auth-secrets-private-keys/)

### Initial Code Execution
- [ActionsTOCTOU (Time Of Check to Time Of Use)](https://github.com/AdnaneKhan/ActionsTOCTOU/) - A tool to monitor for an approval event and then quickly replace a file in the PR head with a local file specified as a parameter.
- [AWS Targeted by a Package Backfill Attack](https://www.mend.io/blog/aws-targeted-by-a-package-backfill-attack/) - Scan commit history for internal packages to execute dependency confusion.
- [Can you trust ChatGPT's package recommendations?](https://vulcan.io/blog/ai-hallucinations-package-risk) - Exploit generative AI platforms' tendency to generate non-existent coding libraries to execute Dependecy Confusion.
- [Can You Trust Your VSCode Extensions?](https://www.aquasec.com/blog/can-you-trust-your-vscode-extensions/) - Impersonate popular VSCode extensions and trick unknowing developers into downloading them.
- [Deep dive into Visual Studio Code extension security vulnerabilities](https://snyk.io/blog/visual-studio-code-extension-security-vulnerabilities-deep-dive/)
- [Dependency Confusion: How I Hacked Into Apple, Microsoft and Dozens of Other Companies](https://medium.com/@alex.birsan/dependency-confusion-4a5d60fec610)
- [Dependency Confusions in Docker and remote pwning of your infra](https://www.errno.fr/DockerDependencyConfusion.html)
- [Erosion of Trust: Unmasking Supply Chain Vulnerabilities in the Terraform Registry](https://boostsecurity.io/blog/erosion-of-trust-unmasking-supply-chain-vulnerabilities-in-the-terraform-registry) - Terraform modules are not protected by the Dependency Lock File, consequently, a seemingly harmless module could potentially introduce malicious code.
- [Fixing typos and breaching microsoft's perimeter](https://johnstawinski.com/2024/04/15/fixing-typos-and-breaching-microsofts-perimeter/) - Bypass GitHub workflow approval requirement by becoming a contributor.
- [GitHub Dataset Research Reveals Millions Potentially Vulnerable to RepoJacking](https://www.aquasec.com/blog/github-dataset-research-reveals-millions-potentially-vulnerable-to-repojacking/)
- [Hacking GitHub AWS integrations again](https://dagrz.com/writing/aws-security/hacking-github-aws-oidc/) - Attacking misconfigured pipelines that use OIDC.
- [How I hacked into Google's internal corporate assets](https://observationsinsecurity.com/2024/04/25/how-i-hacked-into-googles-internal-corporate-assets/) - More ways to find dependencies in code for Dependency Confusion.
- [How to completely own an airline in 3 easy steps](https://maia.crimew.gay/posts/how-to-hack-an-airline/) - Misconfigured CI system accessible from the internet.
- [Introducing MavenGate: a supply chain attack method for Java and Android applications](https://blog.oversecured.com/Introducing-MavenGate-a-supply-chain-attack-method-for-Java-and-Android-applications/) - Many public and popular libraries that have long been abandoned are still being used in huge projects. Access to projects can be hijacked through domain name purchases.
- [Keeping your GitHub Actions and workflows secure Part 1: Preventing pwn requests](https://securitylab.github.com/research/github-actions-preventing-pwn-requests/) - Combining pull_request_target workflow trigger with an explicit checkout of an untrusted PR may lead to repository compromise.
- [Keeping your GitHub Actions and workflows secure Part 2: Untrusted input](https://securitylab.github.com/research/github-actions-untrusted-input/) - GitHub Actions command injection.
- [Malicious code analysis: Abusing SAST (mis)configurations to hack CI systems](https://medium.com/cider-sec/malicious-code-analysis-abusing-sast-mis-configurations-to-hack-ci-systems-13d5c1b37ffe)
- [PPE — Poisoned Pipeline Execution](https://medium.com/cider-sec/ppe-poisoned-pipeline-execution-34f4e8d0d4e9)
- [Security alert: social engineering campaign targets technology industry employees](https://github.blog/2023-07-18-security-alert-social-engineering-campaign-targets-technology-industry-employees/) - Phishing GitHub users.
- [The Monsters in Your Build Cache – GitHub Actions Cache Poisoning](https://adnanthekhan.com/2024/05/06/the-monsters-in-your-build-cache-github-actions-cache-poisoning/)
- [Thousands of npm accounts use email addresses with expired domains](https://therecord.media/thousands-of-npm-accounts-use-email-addresses-with-expired-domains) - Maintainer Email hijacking.
- [Understanding typosquatting methods - for a secure supply chain](https://bytesafe.dev/posts/understanding-typosquatting-methods/)
- [Vulnerable GitHub Actions Workflows Part 1: Privilege Escalation Inside Your CI/CD Pipeline](https://www.legitsecurity.com/blog/github-privilege-escalation-vulnerability) - GitHub Actions workflow_run PE.
- [What the fork? Imposter commits in GitHub Actions and CI/CD](https://www.chainguard.dev/unchained/what-the-fork-imposter-commits-in-github-actions-and-ci-cd)
- [WordPress Plugin Confusion: How an update can get you pwned](https://vavkamil.cz/2021/11/25/wordpress-plugin-confusion-update-can-get-you-pwned/)

### Post Exploitation
- [From Self-Hosted GitHub Runner to Self-Hosted Backdoor](https://www.praetorian.com/blog/self-hosted-github-runners-are-backdoors/)
- [Hacking Terraform State for Privilege Escalation](https://blog.plerion.com/hacking-terraform-state-privilege-escalation/)
- [How We Discovered Vulnerabilities in CI/CD Pipelines of Popular Open-Source Projects](https://cycode.com/blog/github-actions-vulnerabilities) - Extracting all repository and organization secrets in GitHub Actions.
- [Leaking Secrets From GitHub Actions: Reading Files And Environment Variables, Intercepting Network/Process Communication, Dumping Memory](https://karimrahal.com/2023/01/05/github-actions-leaking-secrets/)
- [Living off the pipeline](https://github.com/boostsecurityio/lotp) - Inventory how development tools (typically CLIs), have lesser-known RCE-By-Design features.
<!--lint ignore awesome-list-item-->
- [Registering self-hosted CircleCI runner](broken_links.md/#httpstwittercomalxk7istatus1524353383976558593t5esgwtom2218sgygy5vdoas19) - Can be used to steal secrets of job executed on the malicious runner. 
- [The GitHub Actions Worm: Compromising GitHub Repositories Through the Actions Dependency Tree](https://www.paloaltonetworks.com/blog/prisma-cloud/github-actions-worm-dependencies/)

### Defense Evasion
- [#redteam tip: want to discretely extract credentials from a CI/CD pipeline?](https://twitter.com/_alxk/status/1442519103885959172?s=21) - Draft pull requests won't alert repository contributors, but will still trigger pipelines.
- [Abusing Repository Webhooks to Access Internal CI/CD Systems at Scale](https://www.paloaltonetworks.com/blog/prisma-cloud/repository-webhook-abuse-access-ci-cd-systems-at-scale/)
- [Bypassing required reviews using GitHub Actions](https://medium.com/cider-sec/bypassing-required-reviews-using-github-actions-6e1b29135cc7)
- [Forging signed commits on GitHub](https://iter.ca/post/gh-sig-pwn/)
- [GitHub comments abused to push malware via Microsoft repo URLs](https://www.bleepingcomputer.com/news/security/github-comments-abused-to-push-malware-via-microsoft-repo-urls/) - Hidden GitHub comment link.
- [One Supply Chain Attack to Rule Them All – Poisoning GitHub's Runner Images](https://adnanthekhan.com/2023/12/20/one-supply-chain-attack-to-rule-them-all/)
- [PR sneaking](https://github.com/mortenson/pr-sneaking) - Methods of sneaking malicious code into GitHub pull requests.
- [StarJacking – Making Your New Open Source Package Popular in a Snap](https://checkmarx.com/blog/starjacking-making-your-new-open-source-package-popular-in-a-snap/)
- [The massive bug at the heart of the npm ecosystem](https://blog.vlt.sh/blog/the-massive-hole-in-the-npm-ecosystem) - NPM Manifest Confusion.
- [Trojan Source](https://trojansource.codes/) - Rather than inserting logical bugs, adversaries can attack the encoding of source code files to inject vulnerabilities.
- [Unpinnable Actions: How Malicious Code Can Sneak into Your GitHub Actions Workflows](https://www.paloaltonetworks.com/blog/prisma-cloud/unpinnable-actions-github-security/)
- [Why npm lockfiles can be a security blindspot for injecting malicious modules](https://snyk.io/blog/why-npm-lockfiles-can-be-a-security-blindspot-for-injecting-malicious-modules/)
- [Working as unexpected](https://www.chainguard.dev/unchained/working-as-unexpected) - Creating a GitHub branch that matches a branch protection rule pattern with a workflow file that triggers on push to gain access to environment secrets.
- [Zuckerpunch - Abusing Self Hosted GitHub Runners at Facebook](https://marcyoung.us/post/zuckerpunch/) - Hide commits in a GitHub PR.

## Offensive Tools
- [ADOKit](https://github.com/xforcered/ADOKit) - Azure DevOps Services Attack Toolkit.
- [Gato](https://github.com/praetorian-inc/gato) - GitHub Attack Toolkit.
- [git-dumper](https://github.com/arthaud/git-dumper) - Dump Git repository from a website.
- [GitFive](https://github.com/mxrch/gitfive) - OSINT tool to investigate GitHub profiles.
- [Grep.app](https://grep.app/) - Search GitHub using regex.
- [Jenkins Attack Framework](https://github.com/Accenture/jenkins-attack-framework)
- [Nord Stream](https://github.com/synacktiv/nord-stream) - A tool to extract secrets stored inside CI/CD environments.
- [pwn_jenkins](https://github.com/gquere/pwn_jenkins) - Notes about attacking Jenkins servers.
- [Secrets Patterns Database](https://github.com/mazen160/secrets-patterns-db) - The largest open-source database for detecting secrets, API keys, passwords, tokens, and more. 
- [Sourcegraph](https://sourcegraph.com/search) - A web-based code search and navigation tool for public repositories.
- [Token-Spray](https://blog.projectdiscovery.io/nuclei-v2-5-3-release/) - Automate token validation using Nuclei.

## Case Studies
- [10 real-world stories of how we've compromised CI/CD pipelines](https://research.nccgroup.com/2022/01/13/10-real-world-stories-of-how-weve-compromised-ci-cd-pipelines/)

## Similar Projects
- [Common Threat Matrix for CI/CD Pipeline](https://github.com/rung/threat-matrix-cicd)
- [Open Software Supply Chain Attack Reference (OSC&R)](https://pbom.dev/)
- [Risk Explorer for Software Supply Chains](https://riskexplorer.endorlabs.com/#/attack-tree)
