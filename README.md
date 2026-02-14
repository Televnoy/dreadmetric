<div _ngcontent-ng-c3000883808="" class="immersive-editor markdown stronger mobile" id="null"><div contenteditable="false" translate="no" class="ProseMirror" aria-label="Редактор" aria-busy="false"><h1>DreadMetric Professional</h1><p>Профессиональное веб-приложение (PWA) для расчета стоимости услуг мастера по дредам.</p><h2>Особенности</h2><ul><li><p><strong>Два режима</strong>: Плетение и Коррекция.</p></li><li><p><strong>Лицензирование</strong>: Защита по ключу через Firebase Firestore.</p></li><li><p><strong>Демо-режим</strong>: 60 секунд бесплатного ознакомления.</p></li><li><p><strong>PWA</strong>: Возможность установки на экран «Домой» смартфона.</p></li><li><p><strong>Интерфейс</strong>: Минималистичный дизайн с анимацией частиц и звуковыми эффектами.</p></li></ul><h2>Настройка Firebase</h2><h3>1. Authentication</h3><p>Включите метод входа <strong>Anonymous</strong> в разделе Authentication -&gt; Sign-in method.</p><h3>2. Firestore Database</h3><p>Создайте базу данных и настройте <strong>Rules</strong> (Правила):</p><pre><code>rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /artifacts/rootscalc-pro/{document=**} {
      allow read, write: if request.auth != null;
    }
  }
}
<br class="ProseMirror-trailingBreak"></code></pre><h3>3. Структура данных</h3><p>Создайте коллекцию по пути:
<code>/artifacts/rootscalc-pro/public/data/keys/{KEY_ID}</code></p><p>Внутри документа ключа:</p><ul><li><p><code>usedBy</code>: (string) ID устройства.</p></li><li><p><code>activatedAt</code>: (string/iso-date) дата активации.</p></li></ul><h2>Установка</h2><p>Просто загрузите файлы на GitHub Pages или любой хостинг. Убедитесь, что <code>manifest.json</code> и иконки лежат в корневой папке рядом с <code>index.html</code>.</p></div></div>
