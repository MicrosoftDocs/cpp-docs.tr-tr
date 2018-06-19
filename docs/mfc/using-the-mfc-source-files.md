---
title: Kaynak dosyaları MFC kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- public members
- source files
- MFC, source files
- MFC source files
- comments, MFC
- private member access
- protected member access
- source files, MFC
ms.assetid: 3230e8fb-3b69-4ddf-9538-365ac7ea5e72
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 73177d8b73d5f4be6d886b0bda84f1e1241488cc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384341"
---
# <a name="using-the-mfc-source-files"></a>MFC Kaynak Dosyalarını Kullanma
Microsoft Foundation Class (MFC) kitaplığı tam kaynak kodu sağlar. Üstbilgi dosyaları (.h) \atlmfc\include dizinde bulunan; Uygulama dosyaları (.cpp) kaynağı \atlmfc\src\mfc dizinindedir.  
  
 Bu makaleler ailesi her sınıf çeşitli kısımlarını, bu açıklamalar anlamı ve her bir bölümünde bulmak beklemelisiniz açıklama eklemek için MFC kullanan kuralları açıklar. Visual C++ sihirbazları için oluşturduğunuz sınıfları için benzer kuralları kullanın ve, büyük olasılıkla bu kuralları için kendi kodunuzu yararlı.  
  
 Aşina olabilir **ortak**, `protected`, ve `private` C++ anahtar sözcükleri. MFC üstbilgi dosyalarına bakıldığında, her sınıf birkaç her birinde olabilir bulacaksınız. Örneğin, ortak üye değişkenleri ve işlevleri birden çok altında olması olabilir **ortak** anahtar sözcüğü. MFC üye değişkenleri ve bunların kullanım, izin verilen erişim türüne göre değil dayanarak işlevlerini ayırdığından budur. MFC kullanan `private` tutumlu; uygulama ayrıntılarını genellikle korunur ve birçok kez ortak öğeler bile kabul. Uygulama Ayrıntıları erişimi önerilmez, MFC kararı size bırakır, ancak.  
  
 MFC kaynak dosyalarını ve MFC Uygulama Sihirbazı'nı oluşturur dosyaları içinde (genellikle bu sırayla) Bu sınıf bildirimleri içinde gibi yorumlar bulacaksınız:  
  
 `// Constructors`  
  
 `// Attributes`  
  
 `// Operations`  
  
 `// Overridables`  
  
 `// Implementation`  
  
 Bu makaleler ailesinde kapsanan konular şunlardır:  
  
-   [Açıklamalara bir örnek](../mfc/an-example-of-the-comments.md)  
  
-   [/ / Uygulama açıklaması](../mfc/decrement-implementation-comment.md)  
  
-   [/ / Oluşturucu açıklaması](../mfc/decrement-constructors-comment.md)  
  
-   [/ / Açıklama öznitelikleri](../mfc/decrement-attributes-comment.md)  
  
-   [/ / İşlem açıklaması](../mfc/decrement-operations-comment.md)  
  
-   [/ / Geçersiz kılınabilir açıklama](../mfc/decrement-overridables-comment.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel MFC Konuları](../mfc/general-mfc-topics.md)

