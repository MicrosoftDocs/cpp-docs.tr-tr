---
title: 'Nasıl Yapılır: Durum Çubuğunda Komut Bilgilerini Görüntüleme'
ms.date: 11/04/2016
helpviewer_keywords:
- prompts [MFC]
- displaying command status [MFC]
- status bars [MFC], message area
- status bars [MFC], displaying command information
ms.assetid: de895cbe-61ee-46bf-9787-76b247527d6d
ms.openlocfilehash: 6da45edf611d70920340d8f9a9c2fd8de5cc0307
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50654109"
---
# <a name="how-to-display-command-information-in-the-status-bar"></a>Nasıl Yapılır: Durum Çubuğunda Komut Bilgilerini Görüntüleme

Uygulamanızın çatıyı oluşturmak için Uygulama Sihirbazı'nı çalıştırdığınızda, araç çubuğu ve durum çubuğu destekleyebilir. Uygulama Sihirbazı'nda tek bir seçeneği her ikisini de destekler. Durum çubuğu mevcut olduğunda, kullanıcı işaretçiyi menülerde öğeler üzerinde hareket ederken, uygulama otomatik olarak faydalı geri bildirim sağlar. Menü öğesi vurgulandığında uygulama durum çubuğunda otomatik olarak bir istem dizesi görüntüler. Örneğin, ne zaman kullanıcı hareket işaretçi **Kes** komutunu **Düzenle** menüsünde, durum çubuğundaki ileti alanında durum çubuğu "Seçimi kesip panoya yerleştirir" olarak görüntülenebilir. İstemi kullanıcı menü öğesi amacını anlamalarına yardımcı olur. Kullanıcı bir araç çubuğu düğmesini tıkladığında de çalışır.

Bu durum çubuğu Yardım programa ekleyin menü öğeleri için komut istemi dizeleri tanımlayarak ekleyebilirsiniz. Bunu yapmak için menü düzenleyicisini menü öğesi özelliklerini düzenlerken komut istemi dizeleri sağlar. Tanımladığınız dizeleri uygulama kaynak dosyasında depolanır; Bunlar açıklayan komutları olarak aynı kimlikleri sahiptirler.

Varsayılan olarak, Uygulama Sihirbazı ekler **AFX_IDS_IDLEMESSAGE**, program için yeni iletileri beklediği sırada görüntülenen bir standart "Hazır" ileti kimliği. Uygulama Sihirbazı'nda Context-Sensitive Help seçeneğini belirtirseniz, ileti "Yardım için F1 tuşuna basın için." değiştirilir

## <a name="see-also"></a>Ayrıca Bkz.

[İleti İşleme ve Eşleme](../mfc/message-handling-and-mapping.md)

