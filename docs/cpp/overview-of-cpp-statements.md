---
title: C++ Deyimlerine Genel Bakış
ms.date: 11/04/2016
helpviewer_keywords:
- statements [C++]
ms.assetid: e56996b2-b846-4b99-ac94-ac72fffc5ec7
ms.openlocfilehash: 9493860087331ee2d8ff05a5c0bd59c7a46ad51a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62325565"
---
# <a name="overview-of-c-statements"></a>C++ Deyimlerine Genel Bakış

C++ deyimlerine zaman bir ifade deyimi, bir seçim deyimi, bir yineleme deyimi veya bir atlama deyimi özellikle ilgili dizisini değiştirir dışında ardışık olarak yürütülür.

Deyimlerini aşağıdaki türde olabilir:

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

Çoğu durumda, C++ deyimi sözdizimi, ANSI c aynıdır C dilinde olan iki arasındaki başlıca fark, bildirimlerine yalnızca bir blok başlangıcında izin; C++ ekler *bildirim deyimindeki*, etkili bir şekilde kaldıran bu kısıtlama. Bu, önceden başlatma değeri burada hesaplanabilir programda bir noktada değişkenleri tanıtmak sağlar.

Blokları içindeki değişkenleri bildirme kapsamı ve bu değişkenlerin ömrünü üzerinde kesin denetim uygulamak amacıyla sağlar.

Aşağıdaki C++ anahtar sözcükleri deyimleri konular açıklanmaktadır:

|||||
|-|-|-|-|
|[break](../cpp/break-statement-cpp.md)|[else](../cpp/if-else-statement-cpp.md)|[__if_exists](../cpp/if-exists-statement.md)|[__try](../cpp/structured-exception-handling-c-cpp.md)|
|[case](../cpp/switch-statement-cpp.md)|[__except](../cpp/structured-exception-handling-c-cpp.md)|[__if_not_exists](../cpp/if-not-exists-statement.md)|[deneyin](../cpp/try-throw-and-catch-statements-cpp.md)|
|[Yakalama](../cpp/try-throw-and-catch-statements-cpp.md)|[for](../cpp/for-statement-cpp.md)|[__leave](../c-language/try-finally-statement-c.md)|[while](../cpp/while-statement-cpp.md)|
|[continue](../cpp/continue-statement-cpp.md)|[goto](../cpp/goto-statement-cpp.md)|[return](../cpp/return-statement-cpp.md)||
|[default](../cpp/switch-statement-cpp.md)|[__finally](../cpp/structured-exception-handling-c-cpp.md)|[switch](../cpp/switch-statement-cpp.md)||
|[do](../cpp/do-while-statement-cpp.md)|[Eğer](../cpp/if-else-statement-cpp.md)|[throw](../cpp/try-throw-and-catch-statements-cpp.md)||

## <a name="see-also"></a>Ayrıca bkz.

[Deyimler](../cpp/statements-cpp.md)