# Hybrid Resonant Algorithm (HRA) / Гибридный резонансный алгоритм

> **TL;DR (EN):** Practical cross-domain problem solving via resonance analysis + hybrid ML (RL + GAN + Transformer) with an embedded ethics "sandbox".  
> **Коротко (RU):** Практический междоменный поиск решений на основе резонансного анализа и гибридного ML (RL + GAN + Transformer) с этической «коробкой».

<div align="center">
  
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](#license)
[![Status](https://img.shields.io/badge/status-experimental-orange)]()
[![Python](https://img.shields.io/badge/python-3.9%2B-blue)]()

</div>

## Overview (EN)

- **Core idea:** Identify *resonant* interaction points across domains to collapse exponential search into a tractable polynomial routine.  
- **Architecture:** Generator proposes hypotheses → Resonance check → RL loop updates weights.  
- **Ethics:** Safety-first via an ethics sandbox and directional coefficient Γ to constrain deployment.

> See `docs/ru/report.md` for the full Russian technical report sourced from the author's document.  
> See `docs/en/overview.md` for an English overview and API sketch.

## Обзор (RU)

- **Суть:** Поиск *резонансных* точек взаимодействия между доменами со снижением сложности с экспоненциальной до полиномиальной.  
- **Архитектура:** Генератор гипотез → Резонансная проверка → RL-петля корректирует веса.  
- **Этика:** Этическая «коробка» и коэффициент Γ для безопасного вывода решений.

## Quickstart

```bash
pip install -e .
python examples/python/example_usage.py
```

## Minimal API (draft)

```python
from hra import HRA, ResonanceConfig, EthicsBox

cfg = ResonanceConfig(dim=20, threshold=0.7)
hra = HRA(config=cfg, ethics=EthicsBox(min_level=0.2))

suggestion = hra.propose(x={"domain":"biomed", "goal":"reduce_oxidative_stress"})
score = hra.resonance(suggestion, context={"D":3.2, "q":[...], "m":[...]})
if hra.ethics.ok(score):
    result = hra.apply(suggestion)
```

## Structure

- `src/hra/` — core, resonance, ethics modules
- `docs/ru/report.md` — полный техотчёт (RU)
- `docs/en/overview.md` — краткий обзор (EN)
- `examples/python/` — runnable usage example
- `tests/` — минимальные тесты

## License

MIT — see [LICENSE](LICENSE).
