---
title: --Öznitelikleri yorum | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- comments, Attributes
- Attributes comment in MFC source files
- MFC source files, Attributes comment
- public attributes comment
ms.assetid: 96388e11-42df-4994-aedf-decd152961a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 74398d731c51223ea74fc6b827b0626af89286b5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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

