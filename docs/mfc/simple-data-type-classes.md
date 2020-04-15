---
title: Basit Veri Türü Sınıfları
ms.date: 11/04/2016
f1_keywords:
- vc.classes.data
helpviewer_keywords:
- scalar classes [MFC]
- data classes [MFC]
- simple data type classes [MFC]
ms.assetid: 0d591d68-0a33-49e9-8a6d-90c90de5c16a
ms.openlocfilehash: d4038334e35b734370a437d35519498b96c00770
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365405"
---
# <a name="simple-data-type-classes"></a>Basit Veri Türü Sınıfları

Aşağıdaki sınıflar çizim koordinatlarını, karakter dizelerini ve saat ve tarih bilgilerini saklayarak C++ sözdizimini rahatça kullanmalarını sağlar. Bu nesneler, sınıf kitaplığında Windows sınıflarının üye işlevleri için parametre olarak yaygın olarak kullanılır. `CSize` `CRect` **RECT** **SIZE** **POINT**Windows SDK'da sırasıyla POINT , SIZE ve RECT yapılarına karşılık geldiği için, bu C++ sınıflarının nesnelerini bu C dili yapılarını kullanabileceğiniz her yerde kullanabilirsiniz. `CPoint` Sınıflar, üye işlevleri aracılığıyla yararlı arabirimler sağlar. `CStringT`çok esnek dinamik karakter dizeleri sağlar. `CTime`, `COleDateTime` `CTimeSpan`, `COleTimeSpan` ve saat ve tarih değerlerini temsil. Bu sınıflar hakkında daha fazla bilgi için [Tarih ve Saat](../atl-mfc-shared/date-and-time.md)makalesine bakın.

" "`COle`ile başlayan sınıflar, OLE tarafından sağlanan veri türlerinin kapsülleridir. Bu veri türleri, diğer OLE özelliklerinin kullanılıp kullanılmadığına bakılmaksızın Windows programlarında kullanılabilir.

[CStringT Sınıfı](../atl-mfc-shared/reference/cstringt-class.md)<br/>
Karakter dizeleri tutar.

[Ctime](../atl-mfc-shared/reference/ctime-class.md)<br/>
Mutlak saat ve tarih değerlerini tutar.

[Coledatetime](../atl-mfc-shared/reference/coledatetime-class.md)<br/>
OLE otomasyon türü **DATE**için sarıcı. Tarih ve saat değerlerini temsil eder.

[Ctimespan](../atl-mfc-shared/reference/ctimespan-class.md)<br/>
Göreli saat ve tarih değerlerini tutar.

[COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md)<br/>
İki `COleDateTime` `COleDateTime` değer arasındaki fark gibi göreli değerleri tutar.

[Cpoint](../atl-mfc-shared/reference/cpoint-class.md)<br/>
Koordinat (x, y) çiftlerini tutar.

[Csize](../atl-mfc-shared/reference/csize-class.md)<br/>
Mesafeyi, göreli konumları veya eşleştirilmiş değerleri tutar.

[Crect](../atl-mfc-shared/reference/crect-class.md)<br/>
Dikdörtgen alanların koordinatlarını tutar.

[Cımagelist](../mfc/reference/cimagelist-class.md)<br/>
Windows resim listesinin işlevselliğini sağlar. Resim listeleri liste denetimleri ve ağaç denetimleri ile kullanılır. Aynı boyuttaki bit eşlemleri depolamak ve arşivlemek için de kullanılabilirler.

[Colevariant](../mfc/reference/colevariant-class.md)<br/>
OLE otomasyon tipi **VARIANT**için sarıcı . **VARIANT**s'deki veriler birçok formatta saklanabilir.

[Colecurrency](../mfc/reference/colecurrency-class.md)<br/>
Ondalık noktadan önce 15 basamaklı ve 4 basamak sonra bir sabit nokta aritmetik türü olan OLE otomasyon türü **CURRENCY**için sarıcı.

> [!NOTE]
> `CRect`, `CSize`ve `CPoint` ATL veya MFC uygulamalarında kullanılabilir. Buna ek `CStringT` olarak, MFC `CString`bağımsız -benzeri bir sınıf sağlar. Paylaşılan yardımcı program sınıfları hakkında daha fazla bilgi için [Paylaşılan Sınıflar'a](../atl-mfc-shared/atl-mfc-shared-classes.md)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../mfc/class-library-overview.md)
