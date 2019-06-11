<!-- This file was automatically generated by the `build-harness`. Make all changes to `README.yaml` and run `make readme` to rebuild this file. -->
{{- defineDatasource "config" .Env.README_YAML | regexp.Replace ".*" "" -}}
{{- defineDatasource "includes" .Env.README_INCLUDES | regexp.Replace ".*" "" }}

[![Scale Factory][logo]][website]

# {{(ds "config").name}}{{ if gt (len (ds "config").name) 34 }}{{ print "\n\n" }}{{ end }}{{ if has (ds "config") "badges" }}{{- range $badge := (ds "config").badges -}}{{ printf " [![%s](%s)](%s)" $badge.name $badge.image $badge.url }}{{ end }}{{ end }}

{{ if has (ds "config") "logo" }}
![{{(ds "config").name}}]({{ (ds "config").logo }})
{{- end -}}

{{ if has (ds "config") "description" }}
{{(ds "config").description }}
{{ end }}

---

{{ if has (ds "config") "screenshots" }}
## Screenshots

{{ range $screenshot := (ds "config").screenshots }}
{{ printf "![%s](%s)\n*%s*" $screenshot.name $screenshot.url $screenshot.description }}{{ end }}
{{ end }}
{{ if has (ds "config") "introduction" }}
## Introduction

{{ (ds "config").introduction -}}
{{ end }}
{{ if has (ds "config") "usage" }}
## Usage

{{ (ds "config").usage -}}
{{ end }}
{{ if has (ds "config") "quickstart" -}}
## Quick Start

{{ (ds "config").quickstart -}}
{{ end }}
{{ if has (ds "config") "examples" }}
## Examples

{{(ds "config").examples }}
{{ end }}
{{ if has (ds "config") "include" }}
{{ range $file := (datasource "config").include -}}
{{ (include "includes" $file) }}
{{- end }}
{{- end }}
{{ if has (ds "config") "related" }}

## Share the Love

Like this project? Please give it a ★ on [our GitHub]({{ printf "https://github.com/%s" (ds "config").github_repo}})! (it helps us **a lot**)

## Related Projects

Check out these related projects.
{{ range $related := (ds "config").related }}
{{ printf "- [%s](%s) - %s" $related.name $related.url $related.description }}{{ end }}

{{ end}}
{{ if has (ds "config") "references" }}

## References

For additional context, refer to some of these links.
{{ range $reference := (ds "config").references }}
{{ printf "- [%s](%s) - %s" $reference.name $reference.url $reference.description }}{{ end }}

{{ end}}
## Help

**Got a question?**

File a GitHub [issue]({{ printf "https://github.com/%s/issues" (ds "config").github_repo}}).

## Support & Learning

Work directly with our team of DevOps experts via email, slack, and video conferencing.

We provide [*commercial support*][commercial_support] for all of our [Open Source][github] projects. As a *Dedicated Support* customer, you have access to our team of subject matter experts at a fraction of the cost of a full-time engineer.

[![E-Mail](https://img.shields.io/badge/info@scalefactory.com-blue.svg)][email]

- **Questions.** High performing organisations give their developers
  self-service access to cloud resources. We'll provide a shared Slack channel
  for your team to talk to our cloud experts.
- **The Scale Factory Academy.** Your team will have access to all of our
  hands-on training workshops run through [The Scale Factory
  Academy][scale_factory_academy].
- **Workload reviews.** We'll help you design secure, performance, available and
  cost-effective cloud infrastructure.
- **Incident Support.** We're available 24x7 by support ticket or on the phone, to get you up and running again, and to offer advice on how to avoid similar problems in future.
- **Regular Checkups.** One of our consultants will visit you every month in order to stay up to date with your plans, review any architectural changes you have in mind, and to keep you updated on industry trends.

## Contributing

### Bug Reports & Feature Requests

Please use the [issue tracker]({{ printf "https://github.com/%s/issues" (ds "config").github_repo}}) to report any bugs or file feature requests.

### Developing

We welcome all pull requests to our open source projects. We follow
"fork-and-pull" Git workflow.

 1. **Fork** the repository on GitHub
 2. **Clone** your fork to your local development environment
 3. **Commit** changes to your own branch in your project
 4. **Push** your changes back to GitHub
 5. Submit a **Pull Request** so that we can review your changes

**NOTE:** Be sure to merge the latest changes from "upstream" before making a
pull request!

{{ if has (ds "config") "copyrights" }}

## Copyrights

{{ range $copyright := (ds "config").copyrights -}}
{{ printf "Copyright © %s-%d [%s](%s)\n" $copyright.year time.Now.Year $copyright.name $copyright.url }}
{{ end }}
{{ else }}
## Copyright

Copyright © 2015-{{ time.Now.Year }} [Scale Factory][website]
{{ end}}
{{ if eq (ds "config").license "APACHE2" }}
## License

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

See [LICENSE](LICENSE) for full details.

    Licensed to the Apache Software Foundation (ASF) under one
    or more contributor license agreements.  See the NOTICE file
    distributed with this work for additional information
    regarding copyright ownership.  The ASF licenses this file
    to you under the Apache License, Version 2.0 (the
    "License"); you may not use this file except in compliance
    with the License.  You may obtain a copy of the License at

      https://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing,
    software distributed under the License is distributed on an
    "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
    KIND, either express or implied.  See the License for the
    specific language governing permissions and limitations
    under the License.
{{ end }}

{{ if eq (ds "config").license "MIT" }}
## License

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

The MIT License (MIT)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.

Source: <https://opensource.org/licenses/MIT>
{{ end }}

{{ if eq (ds "config").license "ISC" }}
## License

[![License: ISC](https://img.shields.io/badge/License-ISC-blue.svg)](https://opensource.org/licenses/ISC)

ISC License (ISC)

Permission to use, copy, modify, and/or distribute this software for any purpose with or without fee is hereby granted, provided that the above copyright notice and this permission notice appear in all copies.

THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES WITH REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR ANY SPECIAL, DIRECT, INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF OR IN CONNECTION WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.

Source: <https://opensource.org/licenses/ISC>
{{ end }}

{{ if eq (ds "config").license "GPL3" }}
## License

[![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

GNU GENERAL PUBLIC LICENSE
Version 3, 29 June 2007

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <https://www.gnu.org/licenses/>.
{{ end }}

## About

This project is maintained by [The Scale Factory Ltd.][website]. Like it? Please
give it a ★.

[![Scale Factory][logo]][website]

We're a [DevOps Cloud Infrastructure Consultancy][hire] company based in London,
UK. We love empowering teams to deliver more with [AWS][aws].

We conduct free [AWS Well-Architected Reviews][aws_well_architected] on your AWS
Workloads to ensure that your cloud infrastructure meets the five
well-architected pillars.

We offer [support & learning][commercial_support] to help development teams
deliver more business value.

Check out [our other projects][github], [follow us on twitter][twitter], or [hire us][hire] to help with your cloud strategy and implementation.

{{ if has (datasource "config") "contributors" }}
### Contributors

| {{ range $contributor := (ds "config").contributors }}{{ printf " [![%s][%s_avatar]][%s_homepage]<br/>[%s][%s_homepage] |" $contributor.name $contributor.github $contributor.github $contributor.name $contributor.github}}{{ end }}
|{{- range $contributor := (ds "config").contributors -}}---|{{ end }}

{{ range $contributor := (ds "config").contributors -}}
{{- if has $contributor "homepage" }}
{{ printf "  [%s_homepage]: %s" $contributor.github $contributor.homepage }}
{{ else -}}
{{ printf "  [%s_homepage]: https://github.com/%s" $contributor.github $contributor.github }}
{{ end -}}
{{ if has $contributor "avatar" }}{{ printf "  [%s_avatar]: %s" $contributor.github $contributor.avatar }}
{{ else -}}
{{ printf "  [%s_avatar]: https://github.com/%s.png?size=150" $contributor.github $contributor.github }}
{{- end }}
{{ end }}
{{ end }}


  [logo]: https://www.scalefactory.com/themes/custom/scalefactory/logo.svg
  [website]: https://scalefactory.com
  [github]: https://github.com/scalefactory
  [hire]: https://www.scalefactory.com/services
  [aws_well_architected]: https://www.scalefactory.com/well-architected
  [aws]: https://aws.amazon.com/
  [linkedin]: https://www.linkedin.com/company/the-scale-factory
  [twitter]: https://twitter.com/scalefactory
  [email]: https://www.scalefactory.com/contact-us
  [commercial_support]: https://www.scalefactory.com/services/support-learning
  [scale_factory_academy]: https://www.scalefactory.com/services/training/the-scale-factory-academy
  [share_twitter]: {{ printf "https://twitter.com/intent/tweet/?text=%s&url=https://github.com/%s" ((ds "config").name | regexp.Replace " " "+") (ds "config").github_repo }}
  [share_linkedin]: {{ printf "https://www.linkedin.com/shareArticle?mini=true&title=%s&url=https://github.com/%s" ((ds "config").name | regexp.Replace " " "+") (ds "config").github_repo }}
  [share_reddit]: {{ printf "https://reddit.com/submit/?url=https://github.com/%s" (ds "config").github_repo }}
  [share_facebook]: {{ printf "https://facebook.com/sharer/sharer.php?u=https://github.com/%s" (ds "config").github_repo }}
  [share_email]: {{ printf "mailto:?subject=%s&body=https://github.com/%s" ((ds "config").name | regexp.Replace " " "+") (ds "config").github_repo }}