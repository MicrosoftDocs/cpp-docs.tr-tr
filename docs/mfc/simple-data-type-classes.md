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
ms.openlocfilehash: 4e415805301d7d12bd418a3b55509a7732851492
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62307424"
---
# <a name="simple-data-type-classes"></a>Basit Veri Türü Sınıfları

Aşağıdaki sınıflar çizim koordinatları, karakter dizeleri ve zaman şifreleyebilir ve uygun izin vererek, tarih bilgileri C++ söz dizimini kullanın. Bu nesneler, Sınıf Kitaplığı'nda Windows sınıflarının üye işlevleri için parametre olarak yaygın olarak kullanılır. Çünkü `CPoint`, `CSize`, ve `CRect` karşılık **noktası**, **BOYUTU**, ve **RECT** sırasıyla Windows SDK'da yapıları Bu C dili yapıları kullandığınız her yerde bu C++ sınıfların nesnelerini kullanabilirsiniz. Sınıflar, üye işlevlerini yararlı arabirimlerde sağlar. `CStringT` çok esnek dinamik karakter dizeleri sağlar. `CTime`, `COleDateTime`, `CTimeSpan`, ve `COleTimeSpan` saat ve tarih değerleri temsil eder. Bu sınıflar hakkında daha fazla bilgi için bkz [tarih ve saat](../atl-mfc-shared/date-and-time.md).

Şununla sınıfları "`COle`" encapsulations OLE tarafından sağlanan veri türleri olan. Bu veri türlerini Windows programlar diğer OLE özellikleri kullanılıp bağımsız olarak kullanılabilir.

[CStringT Sınıfı](../atl-mfc-shared/reference/cstringt-class.md)<br/>
Karakter dizeleri içerir.

[CTime](../atl-mfc-shared/reference/ctime-class.md)<br/>
Mutlak tarih değerleri tutar.

[COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)<br/>
OLE Otomasyon türü için sarmalayıcı **tarih**. Tarih ve saat değerlerini temsil eder.

[CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md)<br/>
Göreli tarih değerlerini içerir.

[COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md)<br/>
Göreli tutan `COleDateTime` değerleri, ikisi arasındaki farkı gibi `COleDateTime` değerleri.

[CPoint](../atl-mfc-shared/reference/cpoint-class.md)<br/>
Koordinat (x, y) çiftleri tutar.

[CSize](../atl-mfc-shared/reference/csize-class.md)<br/>
Uzaklık, göreli konumlarını veya eşleştirilmiş değerleri tutar.

[CRect](../atl-mfc-shared/reference/crect-class.md)<br/>
Dikdörtgen alanları koordinatlarını içerir.

[Cımagelist](../mfc/reference/cimagelist-class.md)<br/>
Windows görüntü listesinin işlevlerini sağlar. Görüntü listeleri liste denetimleri ve ağaç denetimleri ile kullanılır. Depolama ve bit eşlemleri aynı boyutlu bir dizi arşivlemek için de kullanılabilir.

[COleVariant](../mfc/reference/colevariant-class.md)<br/>
OLE Otomasyon türü için sarmalayıcı **değişken**. Verileri **değişken**s birçok biçimlerinde depolanabilir.

[COleCurrency](../mfc/reference/colecurrency-class.md)<br/>
OLE Otomasyon türü için sarmalayıcı **para birimi**, ondalık ayırıcıdan önce 15 basamakla ve 4 rakamdan sonra sabit nokta aritmetik türü.

> [!NOTE]
>  `CRect`, `CSize`, ve `CPoint` ATL veya MFC uygulamalarında kullanılabilir. Ayrıca, `CStringT` MFC bağımsız sağlar `CString`-sınıfı ister. Paylaşılan yardımcı sınıflar hakkında daha fazla bilgi için bkz. [paylaşılan sınıflar](../atl-mfc-shared/atl-mfc-shared-classes.md).

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../mfc/class-library-overview.md)
