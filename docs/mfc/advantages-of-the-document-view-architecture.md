---
title: "Belge görünüm mimarisinin avantajları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- views [MFC], advantages
- document/view architecture [MFC], advantages of
ms.assetid: 0bc27071-e120-4889-939c-ce1e61fb9cb3
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6b48166f1002bd5a43325c2838a6d4b5a3626811
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="advantages-of-the-documentview-architecture"></a>Belge/Görünüm Mimarisinin Avantajları
MFC belge/görünüm mimarisinin kullanmanın önemli bir avantajı mimarisi aynı belgenin birden çok görünüm özellikle de desteklemesidir. (Birden çok görünüm gerekmez ve belge/görünüm küçük yükü uygulamanızda aşırı ise, mimarisi önleyebilirsiniz. [Belge/görünüm mimarisinin alternatifleri](../mfc/alternatives-to-the-document-view-architecture.md).)  
  
 Sayısal veri elektronik tablo formunda veya grafik formu görüntülemek kullanıcıların uygulamanızı sağlar varsayalım. Bir kullanıcı aynı anda hem ham verileri, elektronik tablo form ve verileri sonuçları bir grafik görmek isteyebilirsiniz. Bu ayrı görünümleri ayrı çerçeve pencereleri veya tek bir pencere Bölümlendirici bölmelerini görüntüler. Kullanıcının bakın ve elektronik tablo verileri düzenleyip varsayalım şimdi değişiklikleri anında grafikte.  
  
 MFC'de, elektronik tablo ve grafik görünümünde CView türetilmiş farklı sınıflar temel. Her iki görünümde tek bir belge nesne ile ilişkili olabilir. Belge verileri depolar (veya belki de bir veritabanından alır). Her iki görünümde belgeye erişmek ve ondan almak verilerini görüntüleyin.  
  
 Ne zaman bir kullanıcıyı güncelleştirir nesne çağrılarını görüntülemek görünümlerden birini `CDocument::UpdateAllViews`. Bu işlev tüm belgenin görünümlerinin bildirir ve her görünüm belgedeki en son verileri kullanarak kendisini güncelleştirir. Tek çağrısı `UpdateAllViews` farklı görünümleri eşitler.  
  
 Bu senaryoda özellikle görünümleri veri kendilerini depoladıysanız görünümünden zor kodu verileri ayrımını olmadan olacaktır. Belge/görünüm ile kolaydır. Framework koordinasyon işlerin çoğunu sizin için yapar.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Belge/görünüm için alternatifleri](../mfc/alternatives-to-the-document-view-architecture.md)  
  
-   [CDocument](../mfc/reference/cdocument-class.md)  
  
-   [CView](../mfc/reference/cview-class.md)  
  
-   [CDocument::UpdateAllViews](../mfc/reference/cdocument-class.md#updateallviews)  
  
-   [CView::GetDocument](../mfc/reference/cview-class.md#getdocument)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Belge/görünüm mimarisi](../mfc/document-view-architecture.md)

