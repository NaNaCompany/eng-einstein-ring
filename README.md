# 아인슈타인 고리 각반지름 계산기

관측자·점렌즈·광원이 정렬된 근거리 유클리드 기하에서 아인슈타인 고리의 각반지름을 계산한다.

- ID: E106
- App: https://nanalab.kr/eng-einstein-ring/
- Repository: https://github.com/NaNaCompany/eng-einstein-ring
- Formula: θ_E = √[(4GM/c²)(D_S−D_L)/(D_L D_S)]

## Model and data

M>0, D_S>D_L>0. 완전 정렬·점질량·얇은 렌즈·약한장·작은각 근사다. 여기서는 유클리드 거리 D_LS=D_S−D_L를 사용한다. 우주론적 각지름거리에 이 뺄셈을 적용하면 안 된다. 앱은 θ_E≤0.1 rad와 충돌매개변수 b=D_Lθ_E≥100r_s를 요구한다. 광선은 렌즈 물질 바깥을 지나며 가려짐이 없어야 한다. 확장 질량분포·강한장·비정렬·우주 팽창을 제외한다.

Inputs normalize to SI. Repeated-input models support adding/removing actual input rows. Calculations, finite-number checks and physical-domain checks run locally; no external property database or solver API is used.

## Validation

Run node --test tests/*.test.mjs and python scripts/build-locales.py --check. tests/reference.json contains independently computed high-precision default and boundary references. The source notices distinguish original MIT work from citation-only external references.

## Static languages

Korean (existing root), English (`en/`), Spanish (`es/`), Simplified Chinese (`zh/`), Japanese (`ja/`) and German (`de/`). Each page has its own canonical URL, reciprocal hreflang, localized metadata, interface, validation messages and preview image. The language links work without JavaScript. Calculation code is shared and no runtime translation API is used.

Edit `localization/*.json` for text, `src/template.html` for the shared page, and run `python scripts/build-locales.py`. Run `python scripts/build-locales.py --check` and `npm test` before publishing. Decimal commas are accepted in Spanish and German; thousands separators are not supported.
