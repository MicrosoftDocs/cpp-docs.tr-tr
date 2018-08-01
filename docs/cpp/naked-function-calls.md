---
title: Naked işlevi çağrıları | Microsoft Docs
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
ms.openlocfilehash: e395bcb32858bc63b3e848f20a7d794156876e26
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402035"
---
# <a name="naked-function-calls"></a>Çıplak İşlev Çağrıları
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Bildirilen işlevlerin **naked** özniteliğini kullanarak kendi özel giriş/sonuç dizilerinizi yazmak sağlayarak giriş veya çıkış kodu olmadan, yayılan [satır içi assembler](../assembler/inline/inline-assembler.md). Naked işlevleri, Gelişmiş bir özellik olarak sağlanır. Bunlar, C/C++ dışında bir bağlamdan adlı bir işlevi bildirmek etkinleştirmeniz ve böylece farklı parametreler olduğu ya da hangi kayıtlar korunur hakkında varsayımlar. Kesme işleyicileri gibi yordamlar örneklerindendir. Bu özellik, özellikle sanal cihaz sürücülerinin (VXD) yazıcılar için yararlıdır.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
  
-   [naked](../cpp/naked-cpp.md)  
  
-   [Naked İşlevleri için Kurallar ve Sınırlamalar](../cpp/rules-and-limitations-for-naked-functions.md)  
  
-   [Giriş ve bitiş kodu yazmada dikkat edilmesi gerekenler](../cpp/considerations-for-writing-prolog-epilog-code.md)  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Çağırma Kuralları](../cpp/calling-conventions.md)