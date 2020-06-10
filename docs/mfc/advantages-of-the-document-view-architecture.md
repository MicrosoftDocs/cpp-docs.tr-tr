---
title: Belge-görünüm mimarisinin avantajları
ms.date: 11/04/2016
helpviewer_keywords:
- views [MFC], advantages
- document/view architecture [MFC], advantages of
ms.assetid: 0bc27071-e120-4889-939c-ce1e61fb9cb3
ms.openlocfilehash: 80f7141ec62d509defdea361586399bd375df0d1
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84623273"
---
# <a name="advantages-of-the-documentview-architecture"></a>Belge/Görünüm Mimarisinin Avantajları

MFC belge/görünüm mimarisini kullanmanın önemli avantajı, mimarinin aynı belgenin birçok görünümünü özellikle de desteklediğinden emin olur. (Birden çok görünüme ihtiyacınız yoksa ve belge/görünüm küçük ek yükü uygulamanızda daha fazla ise, mimariden kaçınabilirsiniz. [Belge/görünüm mimarisinin alternatifleri](alternatives-to-the-document-view-architecture.md).)

Uygulamanızın, kullanıcıların elektronik tablo biçiminde veya grafik biçiminde sayısal verileri görüntülemesine izin sağladığını varsayalım. Kullanıcı aynı anda hem ham verileri, hem de elektronik tablo formunu ve verilerin sonucu olan bir grafiği görmek isteyebilir. Bu ayrı görünümleri tek bir pencere içinde ayrı çerçeve pencereleri veya ayırıcı bölmelerde görüntüleyebilirsiniz. Artık kullanıcının elektronik tablodaki verileri düzenleyebildiğini ve değişiklikleri grafiğe anında yansıttığını varsayalım.

MFC 'de, elektronik tablo görünümü ve grafik görünümü CView 'dan türetilmiş farklı sınıflara göre yapılır. Her iki görünüm de tek bir belge nesnesiyle ilişkilendirilir. Belge verileri saklar (veya belki bir veritabanından edinir). Her iki görünüm de belgeye erişir ve aldıkları verileri görüntüler.

Bir Kullanıcı görünümlerden birini güncelleştirdiğinde, bu görünüm nesnesi çağırır `CDocument::UpdateAllViews` . Bu işlev tüm belge görünümlerini bildirir ve her görünüm, belgenin en son verilerini kullanarak kendisini güncelleştirir. `UpdateAllViews`Farklı görünümleri eşitleyen tek çağrı.

Bu senaryo, özellikle de verilerin kendisi depolanıyorsa, görünümden veri ayrımı olmadan kod kadar zor olabilir. Belge/görünüm sayesinde bu oldukça kolaydır. Framework, düzenleme işinin çoğunu sizin için işler.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Belge/görünüm alternatifleri](alternatives-to-the-document-view-architecture.md)

- [CDocument](reference/cdocument-class.md)

- [CView](reference/cview-class.md)

- [CDocument:: UpdateAllViews](reference/cdocument-class.md#updateallviews)

- [CView:: GetDocument](reference/cview-class.md#getdocument)

## <a name="see-also"></a>Ayrıca bkz.

[Belge/görünüm mimarisi](document-view-architecture.md)
