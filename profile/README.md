<img src="https://raw.githubusercontent.com/AltairaLabs/.github/main/assets/banner-altairalabs-b.png" alt="AltairaLabs — Own the agent layer. The model is the easy part." width="960">

[![website](https://img.shields.io/badge/website-altairalabs.ai-E3B341?style=flat-square&labelColor=30363d)](https://www.altairalabs.ai)
[![docs](https://img.shields.io/badge/docs-promptpack.org-8B5CF6?style=flat-square&labelColor=30363d)](https://promptpack.org)
[![license](https://img.shields.io/badge/license-Apache--2.0-3B82F6?style=flat-square&labelColor=30363d)](https://www.apache.org/licenses/LICENSE-2.0)
[![self-hosted on kubernetes](https://img.shields.io/badge/self--hosted-kubernetes-326CE5?style=flat-square&labelColor=30363d&logo=kubernetes&logoColor=white)](https://kubernetes.io)

**Build your agent platform in-house** — open, self-hosted, on the infrastructure your team already runs. Author, prove, run and operate agents from one open artifact, on the stack you already trust: Kubernetes, OCI, MCP, OpenTelemetry, Postgres. Rent the models; own the agent layer. No proprietary control plane.

## The instruments

One lifecycle: `author → prove → run → operate`.

<table>
<tr>
<td width="50%" valign="top">
<img src="https://raw.githubusercontent.com/AltairaLabs/.github/main/assets/mark-promptpack.png" width="26" align="left">&nbsp; <a href="https://github.com/AltairaLabs/promptpack-spec"><b>PromptPack</b></a><br>
<sub><code>AUTHOR</code></sub><br>
An open, declarative way to define and package an agent.
</td>
<td width="50%" valign="top">
<img src="https://raw.githubusercontent.com/AltairaLabs/.github/main/assets/mark-promptarena.png" width="26" align="left">&nbsp; <a href="https://github.com/AltairaLabs/promptarena"><b>PromptArena</b></a><br>
<sub><code>PROVE</code></sub><br>
Prove it against simulated users hitting its real tools, in-cluster.
</td>
</tr>
<tr>
<td valign="top">
<img src="https://raw.githubusercontent.com/AltairaLabs/.github/main/assets/mark-promptkit.png" width="26" align="left">&nbsp; <a href="https://github.com/AltairaLabs/PromptKit"><b>PromptKit</b></a><br>
<sub><code>RUN</code></sub><br>
A lean Go runtime for agents — text, voice and video.
</td>
<td valign="top">
<img src="https://raw.githubusercontent.com/AltairaLabs/.github/main/assets/mark-omnia.png" width="26" align="left">&nbsp; <a href="https://omnia.altairalabs.ai"><b>Omnia</b></a><br>
<sub><code>OPERATE</code></sub><br>
Telemetry, memory, governance &amp; compliance, in your own cluster.
</td>
</tr>
</table>

## Why self-hosted

Nothing in here you don't already operate — so your SRE can clear it before anyone signs.

| | |
|---|---|
| **Runs in your cluster** | On your own infrastructure — not a hyperscaler's managed cloud. |
| **Built from what you run** | Kubernetes, OCI, MCP, OpenTelemetry, Postgres. No black box. |
| **Open, inspectable** | Pull it, read it, run it. No proprietary control plane, no lock-in. |

## Prove an agent

Author it, then prove it — simulated users hitting its real tools, with assertions on what it must and must not do. Runs against mock providers, so it needs no API keys.

```console
$ npm install -g @altairalabs/promptarena @altairalabs/packc
$ promptarena init demo --template iot-maintenance-demo
$ cd demo
$ promptarena run -c mock.arena.yaml
```

The demo pack ships a red-team persona that spends five turns trying to reach another tenant's equipment. The assertions hold it to account:

```yaml
conversation_assertions:
  - type: tools_not_called_with_args      # never read another tenant's devices
  - type: tool_calls_with_args            # every call scoped to the active customer
  - type: content_not_includes            # no cross-tenant leakage, no injection echo
```

Results land in `out/report.html`. Add `--format junit` and it gates a pipeline.

> **Own the agent layer.** Your proprietary business logic and your users run in your own cluster — never routed through a vendor's cloud. Models are rented and swappable; the agent layer is where the value accrues, and it stays yours.

---

**[PromptPack](https://github.com/AltairaLabs/promptpack-spec)** &nbsp;·&nbsp; **[PromptArena](https://github.com/AltairaLabs/promptarena)** &nbsp;·&nbsp; **[PromptKit](https://github.com/AltairaLabs/PromptKit)** &nbsp;·&nbsp; **[Omnia](https://omnia.altairalabs.ai)**

Own the agent layer. The model is the easy part. → **[altairalabs.ai](https://www.altairalabs.ai)**
