---
description: 'Daha fazla bilgi edinin: Naked Işlev çağrıları'
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
ms.openlocfilehash: ffc28b65a8c16881164805f0cfa55ffe1bc54e9b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313807"
---
# <a name="naked-function-calls"></a>Çıplak İşlev Çağrıları

**Microsoft'a Özgü**

Özniteliği ile belirtilen işlevler **`naked`** , giriş veya bitiş kodu olmadan dağıtılır ve [satır içi assembler](../assembler/inline/inline-assembler.md)kullanarak kendi özel giriş/bitiş dizilerini yazmanızı sağlar. Naked işlevleri, gelişmiş bir özellik olarak sağlanır. C/C++ dışında bir içerikten çağrılan bir işlevi bildirmenize olanak tanır ve bu nedenle parametrelerin nerede olduğu veya hangi yazmaçların korunduğu konusunda farklı varsayımlar yaparsınız. Örnek, kesme işleyicileri gibi yordamlar içerir. Bu özellik özellikle sanal cihaz sürücülerinin (VxDs) yazarları için yararlıdır.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [naked](../cpp/naked-cpp.md)

- [Çıplak Işlevler için kurallar ve sınırlamalar](../cpp/rules-and-limitations-for-naked-functions.md)

- [Giriş/bitiş kodu yazma konuları](../cpp/considerations-for-writing-prolog-epilog-code.md)

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Çağırma kuralları](../cpp/calling-conventions.md)
