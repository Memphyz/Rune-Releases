# Rune-Releases

O que os apps do **Rune** baixam sem login: eles mesmos e a configuração remota.
O Rune é um app pessoal de streaming em dois APKs — o do celular, que serve o
vídeo, e o da TV, que toca.

**Este repositório não tem código e não roda nada.** Ele guarda o que é
publicado, como anexos de releases de etiqueta fixa. O projeto do Rune fica num
repositório privado, e o GitHub não entrega anexo de release privada sem login.
Como os apps se atualizam sozinhos, sem login, o que eles baixam precisa morar
num repositório público. É para isso que este existe.

---

## As releases

| Etiqueta | O que guarda | Quando muda |
|---|---|---|
| [`phone`](https://github.com/Memphyz/Rune-Releases/releases/tag/phone) | O app do celular, que se atualiza sozinho | A cada versão |
| [`tv`](https://github.com/Memphyz/Rune-Releases/releases/tag/tv) | O app da TV, que se atualiza sozinho | A cada versão |
| [`config`](https://github.com/Memphyz/Rune-Releases/releases/tag/config) | A configuração que os dois apps leem | Quando um serviço troca de domínio |

### `phone` e `tv`

| Arquivo | O que tem |
|---|---|
| `phone-manifest.json` / `tv-manifest.json` | A versão mais recente, o tamanho, o SHA-256 do APK e as notas de cada versão |
| `rune-phone-X.Y.Z.apk` / `rune-tv-X.Y.Z.apk` | O app assinado. Ficam as **três** versões mais novas |

O app confere o manifesto, compara com a versão instalada, mostra as notas e só
instala depois de bater o SHA-256. Quem quiser voltar uma versão instala o APK
anterior à mão.

### `config`

| Arquivo | O que tem |
|---|---|
| `config.json` | Chave do catálogo, domínios dos serviços e limites (pré-buffer, seeds, cache) |

Os apps leem esse arquivo a cada 12 h e guardam o último que deu certo. É por
aqui que um serviço que trocou de domínio volta a funcionar sem publicar app
novo.

---

O corpo de cada release é o changelog da versão, no formato
`## X.Y.Z (AAAA-MM-DD)`, com os grupos **Novidades**, **Melhorias** e
**Correções**.
