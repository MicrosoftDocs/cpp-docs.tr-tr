---
description: 'Daha fazla bilgi edinin: OLE uygulamaları oluşturmak için Işlem dizisi'
title: OLE Uygulamaları Oluşturmak için İşlem Dizisi
ms.date: 11/04/2016
helpviewer_keywords:
- OLE applications [MFC], creating
- OLE applications [MFC]
- applications [OLE], creating
- applications [OLE]
ms.assetid: 84b0f606-36c1-4253-9cea-44427f0074b9
ms.openlocfilehash: 2bce49d569c6d3def536cbe9386cafbe08ccdbfb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217568"
---
# <a name="sequence-of-operations-for-creating-ole-applications"></a>OLE Uygulamaları Oluşturmak için İşlem Dizisi

Aşağıdaki tabloda, OLE bağlama ve ekleme uygulamaları oluşturma bölümünde rolünüzün ve Framework 'ün rolü gösterilmektedir. Bunlar, gerçekleştirilecek adımlar dizisi yerine kullanılabilir seçenekleri temsil eder.

### <a name="creating-ole-applications"></a>OLE uygulamaları oluşturma

|Görev|Bunu yaptığınızda|Çerçeve|
|----------|------------|------------------------|
|COM bileşeni oluşturun.|MFC Uygulama Sihirbazı 'Nı çalıştırın. **Birleşik belge desteği** sekmesinde **tam sunucu** veya **mini sunucu** ' yı seçin.|Framework, COM bileşeni özelliği etkinleştirilmiş bir iskelet uygulaması oluşturur. Tüm COM özellikleri, yalnızca hafif değişikliklerle mevcut uygulamanıza aktarılabilir.|
|Sıfırdan bir kapsayıcı uygulaması oluşturun.|MFC Uygulama Sihirbazı 'Nı çalıştırın. **Birleşik belge desteği** sekmesinde **kapsayıcı** ' yı seçin. sınıf görünümü kullanarak kaynak kodu düzenleyicisine gidin. COM işleyici işlevleriniz için kod girin.|Çerçeve, COM bileşeni (sunucu) uygulamaları tarafından oluşturulan COM nesneleri ekleyebilen bir çatı uygulaması oluşturur.|
|Sıfırdan Otomasyon destekleyen bir uygulama oluşturun.|MFC Uygulama Sihirbazı 'Nı çalıştırın. **Gelişmiş Özellikler** sekmesinden **Otomasyon** ' ı seçin. Otomasyon için uygulamanızdaki yöntemleri ve özellikleri göstermek için sınıf görünümü kullanın.|Çerçeve, diğer uygulamalar tarafından etkinleştirilebilen ve Otomatikleştirilen bir iskelet uygulaması oluşturur.|

## <a name="see-also"></a>Ayrıca bkz.

[Çerçevede derleme](../mfc/building-on-the-framework.md)<br/>
[MFC uygulamaları oluşturmak için Işlem dizisi](../mfc/sequence-of-operations-for-building-mfc-applications.md)<br/>
[ActiveX denetimleri oluşturmak için Işlem dizisi](../mfc/sequence-of-operations-for-creating-activex-controls.md)<br/>
[Veritabanı uygulamaları oluşturmak için Işlem dizisi](../mfc/sequence-of-operations-for-creating-database-applications.md)
