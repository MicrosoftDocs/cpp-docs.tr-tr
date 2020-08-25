---
title: C++ Deyimlerine Genel Bakış
ms.date: 11/04/2016
helpviewer_keywords:
- statements [C++]
ms.assetid: e56996b2-b846-4b99-ac94-ac72fffc5ec7
ms.openlocfilehash: d6bd6b5bb7ba4b83fbed63a40fecc8194cb3707a
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832431"
---
# <a name="overview-of-c-statements"></a>C++ Deyimlerine Genel Bakış

C++ deyimleri sırayla yürütülür, bir ifade deyimi, bir seçim deyimi, yineleme deyimi veya bir sıçrama deyimi özellikle bu sırayı değiştirir.

Deyimler aşağıdaki türlerde olabilir:

> *`labeled-statement`*\
> *`expression-statement`*\
> *`compound-statement`*\
> *`selection-statement`*\
> *`iteration-statement`*\
> *`jump-statement`*\
> *`declaration-statement`*\
> *`try-throw-catch`*

Çoğu durumda, C++ deyimin sözdizimi, ANSI c89 ile aynıdır. İkisi arasındaki birincil fark, c89 içinde yalnızca bir bloğun başlangıcında izin verilir; C++, *`declaration-statement`* Bu kısıtlamayı etkin bir şekilde kaldıran öğesini ekler. Bu, programın önceden hesaplanan başlatma değerinin hesaplanabilecek bir noktada değişkenleri tanıtmanızı sağlar.

Blok içindeki değişkenlerin bildirilmesi, bu değişkenlerin kapsamı ve ömrü üzerinde tam denetim yapmanıza olanak sağlar.

Deyimlerle ilgili makaleler aşağıdaki C++ anahtar sözcüklerini anlatmaktadır:

:::row:::
   :::column span="":::
      [`break`](../cpp/break-statement-cpp.md)\
      [`case`](../cpp/switch-statement-cpp.md)\
      [`catch`](../cpp/try-throw-and-catch-statements-cpp.md)\
      [`continue`](../cpp/continue-statement-cpp.md)\
      [`default`](../cpp/switch-statement-cpp.md)\
      [`do`](../cpp/do-while-statement-cpp.md)
   :::column-end:::
   :::column span="":::
      [`else`](../cpp/if-else-statement-cpp.md)\
      [`__except`](../cpp/structured-exception-handling-c-cpp.md)\
      [`__finally`](../cpp/structured-exception-handling-c-cpp.md)\
      [`for`](../cpp/for-statement-cpp.md)\
      [`goto`](../cpp/goto-statement-cpp.md)
   :::column-end:::
   :::column span="":::
      [`if`](../cpp/if-else-statement-cpp.md)\
      [`__if_exists`](../cpp/if-exists-statement.md)\
      [`__if_not_exists`](../cpp/if-not-exists-statement.md)\
      [`__leave`](../c-language/try-finally-statement-c.md)\
      [`return`](../cpp/return-statement-cpp.md)
   :::column-end:::
   :::column span="":::
      [`switch`](../cpp/switch-statement-cpp.md)\
      [`throw`](../cpp/try-throw-and-catch-statements-cpp.md)\
      [`__try`](../cpp/structured-exception-handling-c-cpp.md)\
      [`try`](../cpp/try-throw-and-catch-statements-cpp.md)\
      [`while`](../cpp/while-statement-cpp.md)
   :::column-end:::
:::row-end:::

## <a name="see-also"></a>Ayrıca bkz.

[Deyimler](../cpp/statements-cpp.md)
