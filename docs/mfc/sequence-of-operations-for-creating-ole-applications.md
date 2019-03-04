---
title: OLE Uygulamaları Oluşturmak için İşlem Dizisi
ms.date: 11/04/2016
helpviewer_keywords:
- OLE applications [MFC], creating
- OLE applications [MFC]
- applications [OLE], creating
- applications [OLE]
ms.assetid: 84b0f606-36c1-4253-9cea-44427f0074b9
ms.openlocfilehash: b7fa989d1a3b799cf6b427e27142d4479be900bf
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57263578"
---
# <a name="sequence-of-operations-for-creating-ole-applications"></a>OLE Uygulamaları Oluşturmak için İşlem Dizisi

Aşağıdaki tabloda, OLE bağlama ve katıştırma uygulamalar oluştururken, rol ve framework'ün rol gösterir. Bunlar gerçekleştirmek için seçenekleri yerine bir dizi adım temsil eder.

### <a name="creating-ole-applications"></a>OLE uygulamaları oluşturma

|Görev|Bunu|Framework yok|
|----------|------------|------------------------|
|Bir COM bileşeni oluşturma.|MFC Uygulama Sihirbazı'nı çalıştırın. Seçin **tam sunucu** veya **Mini sunucu** içinde **bileşik belge desteği** sekmesi.|Framework COM bileşeni özelliği etkin bir çatı uygulaması oluşturur. Tüm COM yeteneğinin mevcut uygulamanıza yalnızca düğümündedir aktarılabilir.|
|Sıfırdan bir kapsayıcı uygulaması oluşturma.|MFC Uygulama Sihirbazı'nı çalıştırın. Seçin **kapsayıcı** içinde **bileşik belge desteği** sekmesi. Sınıf görünümü kullanarak, kaynak kod düzenleyicisine gidin. Kod, COM işleyici işlevleri için doldurun.|Framework COM bileşeni (sunucu) uygulamaları tarafından oluşturulan COM nesnelerini eklemek için iskelet bir uygulama oluşturur.|
|Otomasyon sıfırdan destekleyen bir uygulama oluşturun.|MFC Uygulama Sihirbazı'nı çalıştırın. Seçin **Otomasyon** gelen **Gelişmiş Özellikler** sekmesi. Sınıf Görünümü, yöntemleri ve uygulamanız için Otomasyon özelliklerini göstermek için kullanın.|Framework etkinleştirilir ve diğer uygulamalar tarafından otomatik bir çatı uygulaması oluşturur.|

## <a name="see-also"></a>Ayrıca bkz.

[Framework'te Derleme](../mfc/building-on-the-framework.md)<br/>
[MFC Uygulamaları Oluşturmak için İşlem Dizisi](../mfc/sequence-of-operations-for-building-mfc-applications.md)<br/>
[ActiveX Denetimleri Oluşturmak için İşlem Dizisi](../mfc/sequence-of-operations-for-creating-activex-controls.md)<br/>
[Veritabanı Uygulamaları Oluşturmak için İşlem Dizisi](../mfc/sequence-of-operations-for-creating-database-applications.md)
