---
title: Çıplak işlev çağrıları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- virtual device drivers
- VXD virtual device drivers
- virtual device drivers, naked function calls
- naked functions
- prolog code
- epilog code
- naked keyword [C++]
- naked keyword [C++], storage-class attribute
ms.assetid: 2a66847a-a43f-4541-a7be-c9f5f29b5fdb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b9d7b42f08d68af9838bf908efdbcc59a0540b91
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="naked-function-calls"></a>Çıplak İşlev Çağrıları
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Bildirilen işlevler `naked` özniteliğini kullanarak kendi özel giriş ve bitiş sıraları yazmanızı etkinleştirme giriş veya çıkış kodu olmadan, gösterilen [satır içi derleyicisi](../assembler/inline/inline-assembler.md). Naked işlevleri, Gelişmiş bir özellik olarak sağlanır. Bunlar C/C++ dışında bağlamından adlı bir işlev bildirmek etkinleştirmeniz ve böylece farklı varsayımlar parametreleri olduğu veya hangi yazmaçlar korunur hakkında yapın. Örnekler kesinti işleyicileri gibi yordamları içerir. Bu özellik sanal aygıt sürücüleri (VXD) yazarlar için özellikle yararlıdır.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
  
-   [naked](../cpp/naked-cpp.md)  
  
-   [Naked İşlevleri için Kurallar ve Sınırlamalar](../cpp/rules-and-limitations-for-naked-functions.md)  
  
-   [Giriş ve bitiş kodu yazmada dikkat edilmesi gerekenler](../cpp/considerations-for-writing-prolog-epilog-code.md)  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çağırma Kuralları](../cpp/calling-conventions.md)