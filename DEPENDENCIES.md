# Inventário de Dependências e Segurança da Cadeia de Suprimentos (Supply Chain)

Este documento registra todas as bibliotecas de terceiros utilizadas no **ArcShield**, suas versões exatas, origens confiáveis, licenças de software e hashes criptográficos SHA-256 para verificação de integridade.

---

## 1. Bibliotecas no Repositório

### 1.1 SheetJS (xlsx.full.min.js)
- **Nome do Pacote**: `xlsx` (SheetJS Community Edition)
- **Versão**: `0.18.5`
- **Arquivo Local**: [libs/xlsx.full.min.js](file:///c:/Prog_antigra/ArcFlash/libs/xlsx.full.min.js)
- **Finalidade**: Exportação de dados tabulares de painéis e equipamentos para planilhas eletrônicas no formato Microsoft Excel (`.xlsx`).
- **Origem Oficial**: [https://cdn.sheetjs.com/xlsx-0.18.5/package/dist/xlsx.full.min.js](https://cdn.sheetjs.com/)
- **Licença**: Apache License 2.0
- **Hash de Integridade (SHA-256)**:
  ```text
  C9506197CAF809A075B6DEE1DA0D36FB19DA7158FFE8A88E7B0C96C5D8623C99
  ```
- **Controles de Segurança Implementados**:
  - Processamento estritamente local (client-side).
  - Sanitização de células contra injeção de fórmulas CSV/Excel (células iniciando com `=`, `+`, `-`, `@`).
  - Limites máximos de linhas (500) e colunas (30) para prevenir exaustão de memória.

---

### 1.2 html2canvas (html2canvas.min.js)
- **Nome do Pacote**: `html2canvas`
- **Versão**: `1.4.1`
- **Arquivo Local**: [libs/html2canvas.min.js](file:///c:/Prog_antigra/ArcFlash/libs/html2canvas.min.js)
- **Finalidade**: Rasterização visual do modelo de placa de advertência industrial em elemento `<canvas>` para exportação em imagem PNG de alta resolução e impressão.
- **Origem Oficial**: [https://github.com/niklasvh/html2canvas/releases/tag/v1.4.1](https://github.com/niklasvh/html2canvas)
- **Licença**: MIT License
- **Hash de Integridade (SHA-256)**:
  ```text
  E87E550794322E574A1FDA0C1549A3C70DAE5A93D9113417A429016838EAB8CB
  ```
- **Controles de Segurança Implementados**:
  - `allowTaint: false` e `useCORS: false` para isolamento de dados locais.
  - Sanitização prévia de qualquer imagem SVG inserida antes da renderização no canvas.

---

## 2. Política de Atualização e Monitoramento

1. As dependências são verificadas periodicamente contra os bancos de dados de vulnerabilidades conhecidas (CVE / GitHub Advisory Database / OSV).
2. Não são utilizadas dependências dinâmicas carregadas via CDNs externas em tempo de execução sem pinning de versão e SRI (Subresource Integrity).
3. Todas as bibliotecas necessárias para operação são servidas estaticamente pelo próprio domínio da aplicação (`'self'`).
