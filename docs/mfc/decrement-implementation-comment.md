---
title: --Uygulama açıklaması | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Implementation comment in MFC source files
- comments, MFC
- MFC source files, Implementation comment
- comments, Implementation comments
ms.assetid: 4d799c07-8e71-4a6b-90ab-8282d6ff48ce
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1556c690478b242d929b8a5558264218ddf0b63e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="-implementation-comment"></a>// Uygulama Açıklaması
`// Implementation` Bölüm herhangi MFC sınıf bildiriminin en önemli parçasıdır.  
  
 Bu bölümde, tüm uygulama ayrıntılarını barındırır. Üye değişkenleri ve üye işlevleri bu bölümde yer alabilir. MFC gelecekteki bir sürümde bu satırın altındaki her şeyi değiştirebilir. Bunu yoksayılamaz sürece, aşağıdaki Ayrıntılar güvenmemelisiniz `// Implementation` satır. Bazı uygulama teknik notları ele alınmıştır ancak ek olarak, uygulama satır olarak bildirilen üyeler, açıklanmamıştır. Taban sınıf içinde sanal işlevleri geçersiz kılma bir işlevi temel sınıf uygulamasını geçersiz kılmaları olgu bir uygulama ayrıntılarını olduğu kabul edildiği için bağımsız olarak hangi bölümde temel sınıf işlevi, tanımlanan bu bölümünde bulunur. Genellikle, bu üyeler korunur, ancak her zaman değil.  
  
 Gelen fark `CStdioFile` altında listeleme [açıklamalara bir örnek](../mfc/an-example-of-the-comments.md) üyeleri aşağıda bildirilen `// Implementation` açıklama olarak bildirilebilir **ortak**, `protected`, veya `private`. Gelecekte değişebilir olduğundan dikkatli bir şekilde, bu üyeler yalnızca kullanmanız gerekir. Bir grup üyeleri bildirme **ortak** sınıfı kitaplık uygulaması düzgün çalışması gerekli olabilir. Ancak, bu nedenle bildirilen üyeleri güvenle kullanabilir anlamına gelmez.  
  
> [!NOTE]
>  Üzerinde veya altında kalan türlerinin açıklamaları bulabilirsiniz `// Implementation` açıklama. Her iki durumda da, bunlar bunları bildirilen üyeleri türlerini açıklar. Aşağıda oluşursa `// Implementation` açıklama varsayalım üyeleri MFC sürümleri gelecekte değişebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC kaynak dosyalarını kullanma](../mfc/using-the-mfc-source-files.md)   
 [Açıklamalara bir örnek](../mfc/an-example-of-the-comments.md)   
 [/ / Oluşturucu açıklaması](../mfc/decrement-constructors-comment.md)   
 [Özniteliklerle ilgili açıklama](../mfc/decrement-attributes-comment.md)   
 [/ / İşlem açıklaması](../mfc/decrement-operations-comment.md)   
 [Geçersiz kılınabilir açıklama](../mfc/decrement-overridables-comment.md)

