---
title: "Çıplak işlev çağrıları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
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
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cc02c58479cd52151f697133aa667b6759b5f347
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="naked-function-calls"></a>Çıplak İşlev Çağrıları
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Bildirilen işlevler `naked` özniteliğini kullanarak kendi özel giriş ve bitiş sıraları yazmanızı etkinleştirme giriş veya çıkış kodu olmadan, gösterilen [satır içi derleyicisi](../assembler/inline/inline-assembler.md). Naked işlevleri, Gelişmiş bir özellik olarak sağlanır. Bunlar C/C++ dışında bağlamından adlı bir işlev bildirmek etkinleştirmeniz ve böylece farklı varsayımlar parametreleri olduğu veya hangi yazmaçlar korunur hakkında yapın. Örnekler kesinti işleyicileri gibi yordamları içerir. Bu özellik sanal aygıt sürücüleri (VXD) yazarlar için özellikle yararlıdır.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
  
-   [naked](../cpp/naked-cpp.md)  
  
-   [Naked işlevleri için kurallar ve sınırlamalar](../cpp/rules-and-limitations-for-naked-functions.md)  
  
-   [Giriş ve bitiş kodu yazmada dikkat edilmesi gerekenler](../cpp/considerations-for-writing-prolog-epilog-code.md)  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çağırma kuralları](../cpp/calling-conventions.md)