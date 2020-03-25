---
title: C++ Deyimlerine Genel Bakış
ms.date: 11/04/2016
helpviewer_keywords:
- statements [C++]
ms.assetid: e56996b2-b846-4b99-ac94-ac72fffc5ec7
ms.openlocfilehash: 9aba5deddca6fbf480cd9d573606b16b7ab047db
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188434"
---
# <a name="overview-of-c-statements"></a>C++ Deyimlerine Genel Bakış

C++deyimler, bir ifade deyimi, bir seçim deyimi, yineleme deyimi veya bir atlamanın özel olarak bu sırayı değiştirdiği durumlar dışında sırayla yürütülür.

Deyimler aşağıdaki türlerde olabilir:

```
labeled-statement
expression-statement
compound-statement
selection-statement
iteration-statement
jump-statement
declaration-statement
try-throw-catch
```

Çoğu durumda, C++ deyimin SÖZDIZIMI, ANSI C ile aynıdır. İkisi arasındaki birincil fark C 'de, bildirimlerle yalnızca bir bloğun başlangıcında izin verilir; C++ bu kısıtlamayı etkin bir şekilde kaldıran *bildirim bildirimini*ekler. Bu, programın önceden hesaplanan başlatma değerinin hesaplanabilecek bir noktada değişkenleri tanıtmanızı sağlar.

Blok içindeki değişkenlerin bildirilmesi, bu değişkenlerin kapsamı ve ömrü üzerinde tam denetim yapmanıza olanak sağlar.

Deyimleriyle ilgili konular aşağıdaki C++ anahtar sözcükleri anlatmaktadır:

|||||
|-|-|-|-|
|[break](../cpp/break-statement-cpp.md)|[değilse](../cpp/if-else-statement-cpp.md)|[__if_exists](../cpp/if-exists-statement.md)|[__try](../cpp/structured-exception-handling-c-cpp.md)|
|[case](../cpp/switch-statement-cpp.md)|[__except](../cpp/structured-exception-handling-c-cpp.md)|[__if_not_exists](../cpp/if-not-exists-statement.md)|[almaya](../cpp/try-throw-and-catch-statements-cpp.md)|
|[yakalaya](../cpp/try-throw-and-catch-statements-cpp.md)|[for](../cpp/for-statement-cpp.md)|[__leave](../c-language/try-finally-statement-c.md)|[while](../cpp/while-statement-cpp.md)|
|[continue](../cpp/continue-statement-cpp.md)|[goto](../cpp/goto-statement-cpp.md)|[return](../cpp/return-statement-cpp.md)||
|[default](../cpp/switch-statement-cpp.md)|[__finally](../cpp/structured-exception-handling-c-cpp.md)|[switch](../cpp/switch-statement-cpp.md)||
|[do](../cpp/do-while-statement-cpp.md)|[kullandıysanız](../cpp/if-else-statement-cpp.md)|[throw](../cpp/try-throw-and-catch-statements-cpp.md)||

## <a name="see-also"></a>Ayrıca bkz.

[Deyimler](../cpp/statements-cpp.md)
