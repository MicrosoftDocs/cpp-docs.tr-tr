---
description: 'Daha fazla bilgi edinin: basit veri türü sınıfları'
title: Basit Veri Türü Sınıfları
ms.date: 11/04/2016
f1_keywords:
- vc.classes.data
helpviewer_keywords:
- scalar classes [MFC]
- data classes [MFC]
- simple data type classes [MFC]
ms.assetid: 0d591d68-0a33-49e9-8a6d-90c90de5c16a
ms.openlocfilehash: 4ce6e799cc30dddde18a50802e01c872c54d1d3a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216970"
---
# <a name="simple-data-type-classes"></a>Basit Veri Türü Sınıfları

Aşağıdaki sınıflar çizim koordinatlarını, karakter dizelerini ve zaman ve tarih bilgilerini kapsüllemek için C++ sözdiziminin kullanışlı kullanımına olanak tanır. Bu nesneler, sınıf kitaplığındaki Windows sınıflarının üye işlevlerine parametre olarak yaygın olarak kullanılır. `CPoint`, `CSize` Ve `CRect` sırasıyla **nokta**, **boyut** ve **Rect** yapılarına karşılık gelen Windows SDK, bu C++ sınıflarının nesnelerini, bu C dili yapılarını kullanabileceğiniz her yerde kullanabilirsiniz. Sınıfları, üye işlevleri aracılığıyla yararlı arabirimler sağlar. `CStringT` çok esnek dinamik karakter dizeleri sağlar. `CTime`, `COleDateTime` , `CTimeSpan` , ve `COleTimeSpan` zaman ve tarih değerlerini temsil eder. Bu sınıflar hakkında daha fazla bilgi için bkz. [Tarih ve saat](../atl-mfc-shared/date-and-time.md).

"" İle başlayan sınıflar `COle` OLE tarafından sunulan veri türleri encapsulations. Bu veri türleri, diğer OLE özelliklerinin kullanılıp kullanılmadığına bakılmaksızın Windows programlarında kullanılabilir.

[CStringT sınıfı](../atl-mfc-shared/reference/cstringt-class.md)<br/>
Karakter dizelerini barındırır.

[CTime](../atl-mfc-shared/reference/ctime-class.md)<br/>
Mutlak saat ve tarih değerlerini tutar.

[Cotadatetime](../atl-mfc-shared/reference/coledatetime-class.md)<br/>
OLE Otomasyonu tür **tarihi** için sarmalayıcı. Tarih ve saat değerlerini temsil eder.

[CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md)<br/>
Göreli zaman ve tarih değerlerini tutar.

[Cotadatetimespan](../atl-mfc-shared/reference/coledatetimespan-class.md)<br/>
`COleDateTime`İki değer arasındaki fark gibi göreli değerleri tutar `COleDateTime` .

[CPoint](../atl-mfc-shared/reference/cpoint-class.md)<br/>
Koordinat (x, y) çiftlerini barındırır.

[CSize](../atl-mfc-shared/reference/csize-class.md)<br/>
Uzaklığı, göreli konumları veya eşleştirilmiş değerleri tutar.

[CRect](../atl-mfc-shared/reference/crect-class.md)<br/>
Dikdörtgen alanların koordinatlarını tutar.

[CImageList](../mfc/reference/cimagelist-class.md)<br/>
Windows görüntü listesi işlevlerini sağlar. Görüntü listeleri liste denetimleri ve ağaç denetimleriyle birlikte kullanılır. Aynı zamanda aynı boyutlu bit eşlemlerin bir kümesini depolamak ve arşivlemek için de kullanılabilir.

[Colet varyantı](../mfc/reference/colevariant-class.md)<br/>
OLE Otomasyonu tür **varyantı** için sarmalayıcı. **VARIANT**'lar içindeki veriler birçok biçimde depolanabilir.

[Colet para birimi](../mfc/reference/colecurrency-class.md)<br/>
Sabit noktalı aritmetik tür olan ve sonra ondalık noktadan önce 15 basamakla ve sonrasında 4 basamaktan oluşan OLE Otomasyon türü **para birimi** için sarmalayıcı.

> [!NOTE]
> `CRect`, `CSize` ve, `CPoint` atl ya da MFC uygulamalarında kullanılabilir. Ayrıca, `CStringT` MFC bağımsız benzeri bir sınıf sağlar `CString` . Paylaşılan yardımcı program sınıfları hakkında daha fazla bilgi için bkz. [paylaşılan sınıflar](../atl-mfc-shared/atl-mfc-shared-classes.md).

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../mfc/class-library-overview.md)
