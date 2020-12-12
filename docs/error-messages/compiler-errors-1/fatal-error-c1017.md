---
description: 'Daha fazla bilgi edinin: önemli hata C1017'
title: Önemli Hata C1017
ms.date: 11/04/2016
f1_keywords:
- C1017
helpviewer_keywords:
- C1017
ms.assetid: 5542e604-599d-4e36-8f83-1d454c5753c9
ms.openlocfilehash: a36a5cb11b10ca3ecca00d0379595060918d6a45
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262392"
---
# <a name="fatal-error-c1017"></a>Önemli Hata C1017

geçersiz tamsayı sabiti ifadesi

Bir `#if` yönergedeki ifade yoktu veya bir sabit değer değerlendirmedi.

Kullanılarak tanımlanan sabitler `#define` ,, veya yönergesinde kullanılıyorsa bir tamsayı sabiti değerlendiren değerler içermelidir `#if` `#elif` `#else` .

Aşağıdaki örnek C1017 oluşturur:

```cpp
// C1017.cpp
#define CONSTANT_NAME "YES"
#if CONSTANT_NAME   // C1017
#endif
```

Olası çözüm:

```cpp
// C1017b.cpp
// compile with: /c
#define CONSTANT_NAME 1
#if CONSTANT_NAME
#endif
```

`CONSTANT_NAME`Bir tamsayı değil bir dize olarak değerlendirilir, `#if` yönerge önemli hata C1017 oluşturur.

Diğer durumlarda, Önişlemci tanımsız bir sabiti sıfır olarak değerlendirir. Bu, aşağıdaki örnekte gösterildiği gibi istenmeden sonuçlara neden olabilir. `YES` tanımsız olduğundan sıfır olarak değerlendirilir. İfade `#if` `CONSTANT_NAME` yanlış olarak değerlendirilir ve üzerinde kullanılacak kod ön `YES` işlemci tarafından kaldırılır. `NO` Ayrıca tanımsız (sıfır) olarak değerlendirilir, bu nedenle `#elif` `CONSTANT_NAME==NO` true () olarak değerlendirilir ve `0 == 0` Önişlemci 'nin kodu deyimin bölümünde bırakmasını sağlar; bu da `#elif` amaçlanan davranışın tam tersi olur.

```cpp
// C1017c.cpp
// compile with: /c
#define CONSTANT_NAME YES
#if CONSTANT_NAME
   // Code to use on YES...
#elif CONSTANT_NAME==NO
   // Code to use on NO...
#endif
```

Derleyicinin önişlemci yönergelerini nasıl işleyeceğini tam olarak görmek için [/p](../../build/reference/p-preprocess-to-a-file.md), [/E](../../build/reference/e-preprocess-to-stdout.md)veya [/EP](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)kullanın.
