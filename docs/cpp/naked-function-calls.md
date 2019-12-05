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
ms.openlocfilehash: 242fe83807c6608a09492d0f1f817e3b6e50e530
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857404"
---
# <a name="naked-function-calls"></a>Çıplak İşlev Çağrıları

**Microsoft 'a özgü**

**Naked** özniteliğiyle belirtilen işlevler, giriş veya bitiş kodu olmadan dağıtılır ve [satır içi assembler](../assembler/inline/inline-assembler.md)kullanarak kendi özel giriş/bitiş dizilerini yazmanızı sağlar. Naked işlevleri, gelişmiş bir özellik olarak sağlanır. Bunlar, C/C++dışında bir içerikten Çağrılmakta olan bir işlevi bildirmenize olanak tanır ve bu nedenle parametrelerin nerede olduğu veya hangi yazmaçların korunduğu konusunda farklı varsayımlar yapabilir. Örnek, kesme işleyicileri gibi yordamlar içerir. Bu özellik özellikle sanal cihaz sürücülerinin (VxDs) yazarları için yararlıdır.

## <a name="what-do-you-want-to-know-more-about"></a>Hangi konu hakkında daha fazla bilgi edinmek istiyorsunuz?

- [naked](../cpp/naked-cpp.md)

- [Naked İşlevleri için Kurallar ve Sınırlamalar](../cpp/rules-and-limitations-for-naked-functions.md)

- [Giriş/bitiş kodu yazma konuları](../cpp/considerations-for-writing-prolog-epilog-code.md)

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Çağırma Kuralları](../cpp/calling-conventions.md)