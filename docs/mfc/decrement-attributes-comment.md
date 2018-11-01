---
title: --Özniteliklerle ilgili açıklama
ms.date: 11/04/2016
helpviewer_keywords:
- comments, Attributes
- Attributes comment in MFC source files
- MFC source files, Attributes comment
- public attributes comment
ms.assetid: 96388e11-42df-4994-aedf-decd152961a7
ms.openlocfilehash: 33ee18400e03b55a26c4ad17e8d1ba6853ccda88
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50486079"
---
# <a name="-attributes-comment"></a>// Özniteliklerle İlgili Açıklama

`// Attributes` Ortak öznitelikleri (veya Özellikler) nesnenin bir MFC sınıfı bildirimi bölümü içerir. Genellikle üye değişkenleri veya Get/Set işlevleri şunlardır. "Get" ve "Set" işlevler olabilir veya sanal olabilir. "Get" genellikle işlevlerdir **const**, çoğu durumda, yan etkileri olmadığı. Bu normalde genel üyeleridir; korumalı ve özel öznitelikler genellikle uygulama bölümünde bulunur.

Sınıf listesi örneği'nde `CStdioFile`altında [açıklamalara bir örnek](../mfc/an-example-of-the-comments.md), listede bir üye değişkeni bulunur *m_pStream*. Sınıf `CDC` bu açıklamayı altında yaklaşık 20 üyeleri listeler.

> [!NOTE]
>  Büyük sınıfları, gibi `CDC` ve `CWnd`, yalnızca bir gruptaki tüm öznitelikler listelemek çok açıklık için eklemek kadar çok üyeleri olabilir. Bu gibi durumlarda, sınıf kitaplığı daha üyelerini ayırmak için başlıklarında diğer açıklamaları kullanır. Örneğin, `CDC` kullanan `// Device-Context Functions`, `// Drawing Tool Functions`, `// Drawing Attribute Functions`ve daha fazlası. Yukarıda açıklanan normal söz dizimi özniteliklerini temsil eden gruplarını izler. Adlı bir uygulama bölüm birçok OLE sınıfları sahip `// Interface Maps`.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC Kaynak Dosyalarını Kullanma](../mfc/using-the-mfc-source-files.md)<br/>
[Açıklamalara Bir Örnek](../mfc/an-example-of-the-comments.md)<br/>
[Uygulama açıklaması](../mfc/decrement-implementation-comment.md)<br/>
[/ / Oluşturucu açıklaması](../mfc/decrement-constructors-comment.md)<br/>
[/ / İşlem açıklaması](../mfc/decrement-operations-comment.md)<br/>
[Geçersiz kılınabilen öğelerle ilgili açıklama](../mfc/decrement-overridables-comment.md)

