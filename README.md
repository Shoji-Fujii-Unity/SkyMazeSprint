# Sky Maze Sprint

3D 空中リングスプリント / 3D Sky Flying Ring Sprint

[🇯🇵 日本語](#日本語) · [🇬🇧 English](#english) · [🇪🇸 Español](#español) · [🇵🇹 Português](#português)

---

## 日本語

### 概要
`Sky Maze Sprint` は、PC とスマートフォンでブラウザから遊べる 3D アクションゲームです。
低ポリの空中ステージを飛び、緑のリングを通過しながらゴールゲートを目指します。

### 特徴
- **横長画面固定**：スマホは横画面前提。縦画面では一時停止し、回転案内を表示します。
- **サウンド ON/OFF**：`全体サウンド / BGM / SE` を個別に切り替え可能。
- **多言語対応**：日本語・英語・スペイン語・ポルトガル語。
- **ローカルセーブ**：`localStorage` に進行状況・ハイスコア・設定を保存。
- **ステージ多数**：ステージ番号に応じて自動生成。実質的に長く遊べます。
- **制限時間あり**：時間切れ、またはゴールゲートの先を通過すると敗北。

### 起動方法
1. `index.html` をブラウザで開きます。
2. Three.js を CDN から読み込むため、初回はネットワーク接続が必要です。
3. `file://` で開いて Three.js が読み込めない場合は、ローカルサーバー経由で開いてください。

### 操作方法

#### PC
| 操作 | キー |
|---|---|
| 左右移動 | `A` / `D` / `←` / `→` |
| 上下移動 | `W` / `S` / `↑` / `↓` |
| 上昇補助 | `Space` |
| ブレーキ | `Shift` |
| 一時停止 | `Esc` |

#### スマートフォン
| 操作 | 場所 |
|---|---|
| 移動 | 左下のスティック |
| 上昇 | 右下 `▲` |
| 降下 | 右下 `▼` |
| ブレーキ | 右下 `BRAKE` |
| 一時停止 | 右上 `II` |

### ゲームルール
- 緑のリングを通過するとスコアが増えます。
- 左右の壁に当たるとライフが減ります。
- 黄色いゴールゲートを通るとステージクリアです。
- 制限時間内にゴールできないと敗北です。
- ゴールゲートの先を通過しなかった場合も敗北です。

### 保存データ
`localStorage` のキー `SkyMazeSprint3D_v1` に保存されます。

保存される内容：
- 言語設定
- サウンド設定（Master / BGM / SE）
- 現在のステージ / 解放済みステージ
- ステージごとのベストスコア・ベストタイム
- クリア回数

セーブを削除する場合：
- ブラウザのサイトデータを削除、または
- コンソールで `skyMazeSaveReset()` を実行

### 技術仕様
- 3D：Three.js r149
- サウンド：Web Audio API
- 保存：localStorage
- 画面：横長固定 + 縦画面検出で一時停止
- 多言語：JSON 文字列テーブルで即時切替

### 難易度調整
`loadStage()` 内の `stage.ringRadius` とリング配置振幅を変更すると調整できます。

| 項目 | 標準値 |
|---|---|
| リング半径 | `3.0` |
| 左右振幅 | 最大 `6.0` |
| 上下振幅 | 最大 `4.2` |

---

## English

### Overview
`Sky Maze Sprint` is a 3D action game playable in a browser on PC and smartphones.
Fly through low-poly sky stages, pass green rings, and reach the goal gate.

### Features
- **Landscape fixed**: mobile is designed for landscape. In portrait, the game pauses and shows a rotate prompt.
- **Sound ON/OFF**: `Master / BGM / SFX` can be toggled individually.
- **Multilingual**: Japanese, English, Spanish, Portuguese.
- **Local save**: progress, high scores, and settings are saved to `localStorage`.
- **Many stages**: stages are generated procedurally and can continue for a long time.
- **Time limit**: you fail if time runs out or you miss the goal gate.

### How to Run
1. Open `index.html` in a browser.
2. Three.js is loaded from a CDN, so network access is required on first load.
3. If Three.js fails to load from `file://`, open the game through a local server.

### Controls

#### PC
| Action | Key |
|---|---|
| Move left/right | `A` / `D` / `←` / `→` |
| Move up/down | `W` / `S` / `↑` / `↓` |
| Ascend assist | `Space` |
| Brake | `Shift` |
| Pause | `Esc` |

#### Mobile
| Action | Location |
|---|---|
| Move | Bottom-left stick |
| Ascend | Bottom-right `▲` |
| Descend | Bottom-right `▼` |
| Brake | Bottom-right `BRAKE` |
| Pause | Top-right `II` |

### Rules
- Passing green rings increases your score.
- Hitting side walls reduces lives.
- Passing the yellow goal gate clears the stage.
- You fail if the time limit expires.
- You also fail if you pass beyond the goal gate without clearing.

### Save Data
Saved to `localStorage` under the key `SkyMazeSprint3D_v1`.

Saved contents:
- Language setting
- Sound settings (Master / BGM / SFX)
- Current stage / unlocked stages
- Best score and best time per stage
- Total clears

To delete the save:
- Clear site data in the browser, or
- Run `skyMazeSaveReset()` in the console

### Technical Specs
- 3D: Three.js r149
- Audio: Web Audio API
- Save: localStorage
- Screen: landscape fixed + portrait detection with pause
- i18n: JSON string table with instant switching

### Difficulty Tuning
Adjust `stage.ringRadius` and ring placement amplitude inside `loadStage()`.

| Item | Default |
|---|---|
| Ring radius | `3.0` |
| Horizontal amplitude | max `6.0` |
| Vertical amplitude | max `4.2` |

---

## Español

### Resumen
`Sky Maze Sprint` es un juego de acción 3D jugable en el navegador desde PC y teléfonos.
Vuela por escenarios aéreos de baja poligonización, pasa anillos verdes y llega a la meta.

### Características
- **Pantalla horizontal fija**: en móvil se usa modo horizontal. En vertical, el juego se pausa y muestra un aviso de rotación.
- **Sonido ON/OFF**: `General / BGM / SFX` se activan o desactivan por separado.
- **Multilenguaje**: japonés, inglés, español y portugués.
- **Guardado local**: progreso, récords y ajustes se guardan en `localStorage`.
- **Muchos niveles**: los niveles se generan automáticamente y pueden continuar mucho tiempo.
- **Límite de tiempo**: pierdes si se agota el tiempo o si pasas la meta sin completarla.

### Cómo ejecutar
1. Abre `index.html` en el navegador.
2. Three.js se carga desde CDN, por lo que se necesita conexión la primera vez.
3. Si Three.js no carga desde `file://`, abre el juego a través de un servidor local.

### Controles

#### PC
| Acción | Tecla |
|---|---|
| Mover izquierda/derecha | `A` / `D` / `←` / `→` |
| Mover arriba/abajo | `W` / `S` / `↑` / `↓` |
| Asenso asistido | `Space` |
| Frenar | `Shift` |
| Pausa | `Esc` |

#### Móvil
| Acción | Ubicación |
|---|---|
| Mover | Palanca inferior izquierda |
| Subir | `▲` inferior derecha |
| Bajar | `▼` inferior derecha |
| Frenar | `BRAKE` inferior derecha |
| Pausa | `II` superior derecha |

### Reglas
- Pasar anillos verdes aumenta la puntuación.
- Chocar con las paredes laterales reduce vidas.
- Pasar la meta amarilla supera el nivel.
- Pierdes si se agota el tiempo.
- También pierdes si pasas más allá de la meta sin completarla.

### Datos guardados
Se guardan en `localStorage` con la clave `SkyMazeSprint3D_v1`.

Contenido guardado:
- Idioma
- Ajustes de sonido (General / BGM / SFX)
- Nivel actual / niveles desbloqueados
- Mejor puntuación y mejor tiempo por nivel
- Total de niveles superados

Para borrar el guardado:
- Borra los datos del sitio en el navegador, o
- Ejecuta `skyMazeSaveReset()` en la consola

### Especificaciones técnicas
- 3D: Three.js r149
- Audio: Web Audio API
- Guardado: localStorage
- Pantalla: horizontal fija + detección de vertical con pausa
- Idiomas: tabla JSON con cambio inmediato

### Ajuste de dificultad
Modifica `stage.ringRadius` y la amplitud de colocación de anillos dentro de `loadStage()`.

| Elemento | Valor por defecto |
|---|---|
| Radio del anillo | `3.0` |
| Amplitud horizontal | máx. `6.0` |
| Amplitud vertical | máx. `4.2` |

---

## Português

### Visão geral
`Sky Maze Sprint` é um jogo de ação 3D jogável no navegador em PC e smartphones.
Voe por cenários aéreos de baixa poligonalidade, passe por anéis verdes e alcance o portão de meta.

### Recursos
- **Tela paisagem fixa**: no celular, o jogo é projetado para modo paisagem. Em retrato, pausa e mostra aviso de rotação.
- **Som ON/OFF**: `Principal / BGM / SFX` podem ser ativados ou desativados individualmente.
- **Multilíngue**: japonês, inglês, espanhol e português.
- **Salvamento local**: progresso, recordes e configurações são salvos em `localStorage`.
- **Muitas fases**: as fases são geradas automaticamente e podem continuar por muito tempo.
- **Limite de tempo**: você perde se o tempo acabar ou se passar da meta sem completá-la.

### Como executar
1. Abra `index.html` no navegador.
2. O Three.js é carregado via CDN, então é necessária conexão na primeira vez.
3. Se o Three.js não carregar em `file://`, abra o jogo através de um servidor local.

### Controles

#### PC
| Ação | Tecla |
|---|---|
| Mover esquerda/direita | `A` / `D` / `←` / `→` |
| Mover cima/baixo | `W` / `S` / `↑` / `↓` |
| Subida assistida | `Space` |
| Frear | `Shift` |
| Pausar | `Esc` |

#### Celular
| Ação | Local |
|---|---|
| Mover | Analógico inferior esquerdo |
| Subir | `▲` inferior direito |
| Descer | `▼` inferior direito |
| Frear | `BRAKE` inferior direito |
| Pausar | `II` superior direito |

### Regras
- Passar por anéis verdes aumenta a pontuação.
- Bater nas paredes laterais reduz vidas.
- Passar pelo portão amarelo conclui a fase.
- Você perde se o tempo acabar.
- Também perde se passar além do portão sem concluir.

### Dados salvos
Salvos em `localStorage` com a chave `SkyMazeSprint3D_v1`.

Conteúdo salvo:
- Idioma
- Configurações de som (Principal / BGM / SFX)
- Fase atual / fases desbloqueadas
- Melhor pontuação e melhor tempo por fase
- Total de conclusões

Para apagar o salvamento:
- Limpe os dados do site no navegador, ou
- Execute `skyMazeSaveReset()` no console

### Especificações técnicas
- 3D: Three.js r149
- Áudio: Web Audio API
- Salvamento: localStorage
- Tela: paisagem fixa + detecção de retrato com pausa
- Idiomas: tabela JSON com troca imediata

### Ajuste de dificuldade
Ajuste `stage.ringRadius` e a amplitude de posicionamento dos anéis dentro de `loadStage()`.

| Item | Valor padrão |
|---|---|
| Raio do anel | `3.0` |
| Amplitude horizontal | máx. `6.0` |
| Amplitude vertical | máx. `4.2` |