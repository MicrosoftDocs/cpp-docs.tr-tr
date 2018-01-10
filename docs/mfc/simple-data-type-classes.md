---
title: "Basit veri türü sınıfları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.data
dev_langs: C++
helpviewer_keywords:
- scalar classes [MFC]
- data classes [MFC]
- simple data type classes [MFC]
ms.assetid: 0d591d68-0a33-49e9-8a6d-90c90de5c16a
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d2b4df05d64cb97032477ca50ff4b0ce572829b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="simple-data-type-classes"></a>Basit Veri Türü Sınıfları
Aşağıdaki sınıflar çizim koordinatları, karakter dizelerini ve saat şifreleyebilir ve uygun tarih bilgilerini C++ söz dizimini kullanın. Bu nesneler, Sınıf Kitaplığı'nda Windows sınıfların üye işlevleri için parametre olarak yaygın olarak kullanılır. Çünkü `CPoint`, `CSize`, ve `CRect` karşılık **noktası**, **BOYUTU**, ve `RECT` yapıları, sırasıyla, Windows SDK'ın bu nesnelerin kullanabilirsiniz Bu C dil yapıları kullanabilirsiniz her yerde C++ sınıfları. Üye işlevlerini yararlı arabirimlerde sınıflar sağlar. `CStringT`çok esnek dinamik karakter dizelerini sağlar. `CTime`, `COleDateTime`, `CTimeSpan`, ve **COleTimeSpan** saat ve tarih değerleri temsil eder. Makaleyi bu sınıfları hakkında daha fazla bilgi için bkz: [tarih ve saat](../atl-mfc-shared/date-and-time.md).  
  
 İle başlayan sınıfları "**COle**" encapsulations OLE tarafından sağlanan veri türleri şunlardır. Bu veri türleri Windows programlarında diğer OLE özellikleri kullanılıp bağımsız olarak kullanılabilir.  
  
 [CStringT Sınıfı](../atl-mfc-shared/reference/cstringt-class.md)  
 Karakter dizelerini içerir.  
  
 [CTime](../atl-mfc-shared/reference/ctime-class.md)  
 Mutlak saat ve tarih değerlerinin tutar.  
  
 [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)  
 OLE Otomasyon türü için sarmalayıcı **tarih**. Tarih ve saat değerlerini temsil eder.  
  
 [CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md)  
 Göreli saat ve tarih değerlerinin tutar.  
  
 [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md)  
 Göreli tutan `COleDateTime` değerleri, ikisi arasındaki farkı gibi `COleDateTime` değerleri.  
  
 [CPoint](../atl-mfc-shared/reference/cpoint-class.md)  
 Ayrı tutma (x, y) koordinat çiftleri.  
  
 [CSize](../atl-mfc-shared/reference/csize-class.md)  
 Uzaklık, göreli konumları ya da eşleştirilmiş değerleri barındırır.  
  
 [CRect](../atl-mfc-shared/reference/crect-class.md)  
 Dikdörtgen alanları koordinatlarını içerir.  
  
 [Cımagelist](../mfc/reference/cimagelist-class.md)  
 Windows görüntü listesi işlevselliğini sağlar. Görüntü listeleri liste denetimleri ve ağaç denetimleri ile kullanılır. Depolamak ve bit eşlemler aynı boyuta sahip bir dizi arşivlemek için de kullanılabilir.  
  
 [COleVariant](../mfc/reference/colevariant-class.md)  
 OLE Otomasyon türü için sarmalayıcı **değişken**. Verileri **değişken**s birçok biçimlerinde depolanabilir.  
  
 [COleCurrency](../mfc/reference/colecurrency-class.md)  
 OLE Otomasyon türü için sarmalayıcı **para birimi**, 15 basamağa ondalık ayırıcıdan önce ve sonra 4 basamaklı bir sabit noktalı aritmetik türü.  
  
> [!NOTE]
>  `CRect`, `CSize`, ve `CPoint` ATL veya MFC uygulamalarında kullanılabilir. Ayrıca, `CStringT` MFC bağımsız sağlar `CString`-ister sınıfı. Paylaşılan yardımcı sınıfları hakkında daha fazla bilgi için bkz: [paylaşılan sınıfları](../atl-mfc-shared/atl-mfc-shared-classes.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../mfc/class-library-overview.md)

