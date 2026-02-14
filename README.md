# **DreadMetric Professional**

Профессиональное веб\-приложение (PWA) для расчета стоимости услуг мастера по дредам.

## **Особенности**

* **Два режима**: Плетение и Коррекция.  
* **Лицензирование**: Защита по ключу через Firebase Firestore.  
* **Демо-режим**: 60 секунд бесплатного ознакомления.  
* **PWA**: Возможность установки на экран «Домой» смартфона.  
* **Интерфейс**: Минималистичный дизайн с анимацией частиц и звуковыми эффектами.

## **Настройка Firebase**

### **1\. Authentication**

Включите метод входа **Anonymous** в разделе Authentication \-\> Sign-in method.

### **2\. Firestore Database**

Создайте базу данных и настройте **Rules** (Правила):

rules\_version \= '2';  
service cloud.firestore {  
  match /databases/{database}/documents {  
    match /artifacts/rootscalc-pro/{document=\*\*} {  
      allow read, write: if request.auth \!= null;  
    }  
  }  
}

### **3\. Структура данных**

Создайте коллекцию по пути:

/artifacts/rootscalc-pro/public/data/keys/{KEY\_ID}

Внутри документа ключа:

* usedBy: (string) ID устройства.  
* activatedAt: (string/iso-date) дата активации.

## **Установка**

Просто загрузите файлы на GitHub Pages или любой хостинг. Убедитесь, что manifest.json и иконки лежат в корневой папке рядом с index.html.