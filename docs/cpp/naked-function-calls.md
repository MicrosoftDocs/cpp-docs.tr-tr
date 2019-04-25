---
title: Çıplak İşlev Çağrıları
ms.date: 11/04/2016
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
ms.openlocfilehash: f9d8a8747d4a808d040b814005782ed8187bf274
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301584"
---
# <a name="naked-function-calls"></a>Çıplak İşlev Çağrıları

## <a name="microsoft-specific"></a>Microsoft'a Özgü

Bildirilen işlevlerin **naked** özniteliğini kullanarak kendi özel giriş/sonuç dizilerinizi yazmak sağlayarak giriş veya çıkış kodu olmadan, yayılan [satır içi assembler](../assembler/inline/inline-assembler.md). Naked işlevleri, Gelişmiş bir özellik olarak sağlanır. Bunlar, C/C++ dışında bir bağlamdan adlı bir işlevi bildirmek etkinleştirmeniz ve böylece farklı parametreler olduğu ya da hangi kayıtlar korunur hakkında varsayımlar. Kesme işleyicileri gibi yordamlar örneklerindendir. Bu özellik, özellikle sanal cihaz sürücülerinin (VXD) yazıcılar için yararlıdır.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [naked](../cpp/naked-cpp.md)

- [Naked İşlevleri için Kurallar ve Sınırlamalar](../cpp/rules-and-limitations-for-naked-functions.md)

- [Giriş ve bitiş kodu yazmada dikkat edilmesi gerekenler](../cpp/considerations-for-writing-prolog-epilog-code.md)

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Çağırma Kuralları](../cpp/calling-conventions.md)