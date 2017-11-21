---
title: "--Öznitelikleri yorum | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- comments, Attributes
- Attributes comment in MFC source files
- MFC source files, Attributes comment
- public attributes comment
ms.assetid: 96388e11-42df-4994-aedf-decd152961a7
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c93d27cb5a9c6ef83f5b4f027d0e54cbe69a6bbd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="-attributes-comment"></a>// Özniteliklerle İlgili Açıklama
`// Attributes` Ortak öznitelikleri (veya özellikleri) nesnesinin bir MFC sınıf bildirimi bölümü içerir. Genellikle üye değişkenleri veya Get/Set işlevler şunlardır. "Get" ve "Ayarla" işlevleri olabilir veya sanal olabilir. "Get" genellikle işlevlerdir **const**, çoğu durumda bunlar yan etkileri olmadığı için. Bu üyeleri normalde ortak; korumalı ve özel öznitelikleri genellikle uygulama bölümünde bulunur.  
  
 Sınıfından listeleme örnekteki `CStdioFile`altında [açıklamalara bir örnek](../mfc/an-example-of-the-comments.md), listeden bir üye değişkeni içerir `m_pStream`. Sınıf `CDC` bu açıklama altında yaklaşık 20 üyeleri listeler.  
  
> [!NOTE]
>  Gibi büyük sınıfları `CDC` ve `CWnd`, yalnızca bir gruptaki tüm öznitelikler listesi çok daha anlaşılır olması için eklediğiniz değil çok fazla sayıda üyeleri olabilir. Böyle durumlarda, sınıf kitaplığı daha fazla üyeleri ayırmak için başlıklarında diğer yorumlar kullanır. Örneğin, `CDC` kullanan `// Device-Context Functions`, `// Drawing Tool Functions`, `// Drawing Attribute Functions`ve daha fazlası. Yukarıda açıklanan her zamanki sözdizimi özniteliklerini temsil eden gruplarını izler. Adlı bir uygulama bölüm birçok OLE sınıfları sahip `// Interface Maps`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC kaynak dosyalarını kullanma](../mfc/using-the-mfc-source-files.md)   
 [Açıklamalara bir örnek](../mfc/an-example-of-the-comments.md)   
 [Uygulama açıklaması](../mfc/decrement-implementation-comment.md)   
 [/ / Oluşturucu açıklaması](../mfc/decrement-constructors-comment.md)   
 [/ / İşlem açıklaması](../mfc/decrement-operations-comment.md)   
 [Geçersiz kılınabilir açıklama](../mfc/decrement-overridables-comment.md)

