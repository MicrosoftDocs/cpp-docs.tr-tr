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
ms.openlocfilehash: 14bc64314cf64e7d13c076c314419e3d636432d7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177943"
---
# <a name="naked-function-calls"></a>Çıplak İşlev Çağrıları

**Microsoft 'a özgü**

**Naked** özniteliğiyle belirtilen işlevler, giriş veya bitiş kodu olmadan dağıtılır ve [satır içi assembler](../assembler/inline/inline-assembler.md)kullanarak kendi özel giriş/bitiş dizilerini yazmanızı sağlar. Naked işlevleri, gelişmiş bir özellik olarak sağlanır. Bunlar, C/C++dışında bir içerikten Çağrılmakta olan bir işlevi bildirmenize olanak tanır ve bu nedenle parametrelerin nerede olduğu veya hangi yazmaçların korunduğu konusunda farklı varsayımlar yapabilir. Örnek, kesme işleyicileri gibi yordamlar içerir. Bu özellik özellikle sanal cihaz sürücülerinin (VxDs) yazarları için yararlıdır.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [naked](../cpp/naked-cpp.md)

- [Naked İşlevleri için Kurallar ve Sınırlamalar](../cpp/rules-and-limitations-for-naked-functions.md)

- [Giriş/bitiş kodu yazma konuları](../cpp/considerations-for-writing-prolog-epilog-code.md)

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Çağırma Kuralları](../cpp/calling-conventions.md)
