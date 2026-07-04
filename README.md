<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>休み希望フォーム（ver3.3）使い方ガイド</title>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    body {
      background-color: #EAF2F5;
      color: #1E2D3A;
      font-family: 'Hiragino Kaku Gothic ProN', 'Noto Sans JP', sans-serif;
      font-size: 15px;
      line-height: 1.6;
      -webkit-font-smoothing: antialiased;
      padding: 24px 12px 60px;
    }
    .wrapper {
      max-width: 480px;
      margin: 0 auto;
    }
    .main-header {
      background: linear-gradient(135deg, #2A7D9C 0%, #1a8fa8 100%);
      color: white;
      padding: 32px 20px;
      border-radius: 16px 16px 0 0;
      text-align: center;
      box-shadow: 0 4px 12px rgba(42,125,156,.15);
    }
    .main-header h1 {
      font-size: 22px;
      font-weight: 800;
      letter-spacing: 0.05em;
      margin-bottom: 6px;
    }
    .main-header .subtitle {
      font-size: 12px;
      color: rgba(255, 255, 255, 0.8);
      font-weight: 600;
      background: rgba(255, 255, 255, 0.15);
      padding: 3px 12px;
      border-radius: 20px;
      display: inline-block;
    }
    .intro-card {
      background: white;
      padding: 20px;
      border-radius: 0 0 16px 16px;
      margin-bottom: 24px;
      box-shadow: 0 4px 12px rgba(42,125,156,.05);
      font-size: 14px;
      color: #566B7A;
    }
    .section-title {
      font-size: 16px;
      color: #1F5F78;
      font-weight: 800;
      margin: 32px 0 16px;
      display: flex;
      align-items: center;
      gap: 8px;
    }
    .section-title::before {
      content: "";
      width: 6px;
      height: 18px;
      background: #4BBFA0;
      border-radius: 3px;
      display: inline-block;
    }
    .step-card {
      background: white;
      border-radius: 14px;
      padding: 20px;
      margin-bottom: 20px;
      box-shadow: 0 4px 14px rgba(42,125,156,.06);
      position: relative;
    }
    .step-badge {
      background: #2A7D9C;
      color: white;
      font-size: 11px;
      font-weight: 800;
      padding: 3px 10px;
      border-radius: 20px;
      display: inline-block;
      margin-bottom: 12px;
    }
    .step-text h3 {
      font-size: 16px;
      font-weight: 800;
      color: #1E2D3A;
      margin-bottom: 8px;
    }
    .step-text p {
      font-size: 14px;
      color: #4A5966;
      margin-bottom: 14px;
    }
    /* 画像表示エリア（実画像がない場合はオシャレなプレースホルダーを表示） */
    .image-container {
      width: 100%;
      background: #F2F7F9;
      border: 2px dashed #D3E4EC;
      border-radius: 10px;
      overflow: hidden;
      margin: 12px 0;
      position: relative;
      display: flex;
      align-items: center;
      justify-content: center;
    }
    .image-container img {
      width: 100%;
      height: auto;
      display: block;
      object-fit: cover;
    }
    /* 画像未設定時のダミーテキスト */
    .image-placeholder-text {
      position: absolute;
      color: #7A8F9C;
      font-size: 12px;
      font-weight: 600;
      text-align: center;
      pointer-events: none;
      padding: 40px 10px;
    }
    .img-aspect-tall { aspect-ratio: 4 / 3; }
    .img-aspect-short { aspect-ratio: 16 / 9; }

    .bullet-list {
      list-style: none;
      background: #F7FAFC;
      padding: 12px;
      border-radius: 8px;
      margin-top: 10px;
    }
    .bullet-list li {
      font-size: 13px;
      color: #4A5966;
      position: relative;
      padding-left: 14px;
      margin-bottom: 6px;
    }
    .bullet-list li:last-child { margin-bottom: 0; }
    .bullet-list li::before {
      content: "•";
      color: #4BBFA0;
      position: absolute;
      left: 2px;
      font-weight: bold;
    }
    .alert-box {
      background: #FFF5F5;
      border-left: 4px solid #D64045;
      padding: 12px;
      border-radius: 0 8px 8px 0;
      font-size: 13px;
      margin-top: 12px;
      color: #662224;
    }
    .alert-title { font-weight: 800; margin-bottom: 2px; }

    .feature-grid {
      display: grid;
      grid-template-columns: 1fr;
      gap: 12px;
    }
    .feature-item {
      background: white;
      padding: 16px;
      border-radius: 12px;
      box-shadow: 0 4px 12px rgba(42,125,156,.04);
      display: flex;
      gap: 12px;
      align-items: flex-start;
    }
    .feature-icon {
      font-size: 24px;
      background: #EAF4F7;
      width: 44px;
      height: 44px;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      flex-shrink: 0;
    }
    .feature-info h4 { font-size: 14px; font-weight: 800; color: #2A7D9C; margin-bottom: 2px; }
    .feature-info p { font-size: 12px; color: #566B7A; }

    .footer {
      text-align: center;
      font-size: 11px;
      color: #7A8F9C;
      margin-top: 40px;
      padding-top: 20px;
      border-top: 1px solid #D3E4EC;
    }
  </style>
</head>
<body>

<div class="wrapper">
  
  <div class="main-header">
    <h1>休み希望フォーム</h1>
    <div class="subtitle">スタッフ専用・使い方ガイド ver3.3</div>
  </div>
  
  <div class="intro-card">
    <p>LINEからいつでも1タップで起動。店舗スタッフの皆様が「かんたん」「スムーズ」にシフトの休み希望を提出・管理できるように作られた専用ページです。</p>
  </div>

  <div class="section-title">✨ このツールの便利な特徴</div>
  <div class="feature-grid">
    <div class="feature-item">
      <div class="feature-icon">👤</div>
      <div class="feature-info">
        <h4>ログイン作業は不要</h4>
        <p>LINEから開くだけであなたの名前を自動認識。IDやパスワードを入れる手間がありません。</p>
      </div>
    </div>
    <div class="feature-item">
      <div class="feature-icon">📦</div>
      <div class="feature-info">
        <h4>何日分でも、まとめて1回で送信</h4>
        <p>希望日をポンポンとリストに登録していき、最後に「1回押すだけ」でまとめて申請できます。</p>
      </div>
    </div>
    <div class="feature-item">
      <div class="feature-icon">📜</div>
      <div class="feature-info">
        <h4>手元に残る「自動履歴」</h4>
        <p>過去にいつ、どんな内容を送信したかがスマホ内に自動保存され、いつでも見返せます。</p>
      </div>
    </div>
  </div>

  <div class="section-title">🛠️ 基本的な操作手順</div>

  <!-- STEP 1 -->
  <div class="step-card">
    <span class="step-badge">STEP 01</span>
    <div class="step-text">
      <h3>休み希望日を選択する</h3>
      <p>画面上部にある<b>「📅 休み希望日を追加」</b>ボタンをタップし、表示されるカレンダーから休みたい日付を選びます。</p>
    </div>
    <div class="image-container img-aspect-short">
      <div class="image-placeholder-text">【ここに step1.png を配置】<br>カレンダー起動ボタンのスクショ</div>
      <img src="step1.png" alt="" onerror="this.style.display='none'">
    </div>
  </div>

  <!-- STEP 2 -->
  <div class="step-card">
    <span class="step-badge">STEP 02</span>
    <div class="step-text">
      <h3>詳細を入力して「決定」する</h3>
      <p>日付を選ぶと下に青い下書きエリアが現れます。各項目を選択・入力し、最後に<b>「決定」</b>ボタンをタップして確定させます。</p>
      <ul class="bullet-list">
        <li><b>TIME ZONE：</b>午前/午後/終日から選択（時間の自由入力も可能）</li>
        <li><b>希望内容：</b>公休/有休/振休/欠勤から選択（必須）</li>
        <li><b>理由・メモ：</b>管理者に伝えたい連絡事項を入力（任意）</li>
      </ul>
    </div>
    <div class="image-container img-aspect-tall">
      <div class="image-placeholder-text">【ここに step2.png を配置】<br>詳細入力欄（下書きカード）のスクショ</div>
      <img src="step2.png" alt="" onerror="this.style.display='none'">
    </div>
    <div class="alert-box">
      <div class="alert-title">💡 日付や内容を間違えたときは？</div>
      決定を押すと予定が下に追加されます。右上の「✕」ボタンを押せばその場でいつでも取り消せます。
    </div>
  </div>

  <!-- STEP 3 -->
  <div class="step-card">
    <span class="step-badge">STEP 03</span>
    <div class="step-text">
      <h3>最後に「送信ボタン」を押す</h3>
      <p>希望日をすべて登録し終えたら、一番下にある緑色の<b>「休み希望を送信する」</b>ボタンをタップします。「送信しました ✓」と表示されれば完了です！</p>
    </div>
    <div class="image-container img-aspect-short">
      <div class="image-placeholder-text">【ここに step3.png を配置】<br>一番下の送信ボタンのスクショ</div>
      <img src="step3.png" alt="" onerror="this.style.display='none'">
    </div>
  </div>

  <div class="section-title">🕒 過去の申請履歴を見る</div>
  <div class="step-card">
    <div class="step-text">
      <p>画面の最下部にある「送信履歴」エリアでは、これまでに自分が送ったデータを確認できます。</p>
      <ul class="bullet-list">
        <li>何月何日に何日分の希望を送ったかが一目でわかります。</li>
        <li>個別の「✕」ボタンを押すことで、不要になった過去の履歴を整理したり、管理側に削除要求を出すことができます。</li>
      </ul>
    </div>
    <div class="image-container img-aspect-short">
      <div class="image-placeholder-text">【ここに step4.png を配置】<br>送信履歴エリアのスクショ</div>
      <img src="step4.png" alt="" onerror="this.style.display='none'">
    </div>
  </div>

  <div class="footer">
    © 薬局スタッフ専用シフト管理システムサポート
  </div>

</div>

</body>
</html>
