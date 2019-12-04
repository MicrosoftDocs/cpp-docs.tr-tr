---
title: Önemli Hata C1017
ms.date: 11/04/2016
f1_keywords:
- C1017
helpviewer_keywords:
- C1017
ms.assetid: 5542e604-599d-4e36-8f83-1d454c5753c9
ms.openlocfilehash: 0feda3bc4c3729d3101be356220aa0124ba85190
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756948"
---
# <a name="fatal-error-c1017"></a>Önemli Hata C1017

geçersiz tamsayı sabiti ifadesi

`#if` yönergesinin ifadesi yoktu veya bir sabit değer olarak değerlendirilmedi.

`#define` kullanılarak tanımlanan sabitler, bir `#if`, `#elif`veya `#else` yönergesinde kullanılıyorsa bir tamsayı sabiti değerlendiren değerler içermelidir.

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

`CONSTANT_NAME` bir tamsayı değil bir dizeye göre değerlendirildiği için `#if` yönergesi önemli hata C1017 oluşturur.

Diğer durumlarda, Önişlemci tanımsız bir sabiti sıfır olarak değerlendirir. Bu, aşağıdaki örnekte gösterildiği gibi istenmeden sonuçlara neden olabilir. `YES` tanımsız olduğundan, sıfır olarak değerlendirilir. `#if` `CONSTANT_NAME` ifadesi yanlış olarak değerlendirilir ve `YES` üzerinde kullanılacak kod Önişlemci tarafından kaldırılır. `NO` de tanımsız (sıfır), bu nedenle `#elif` `CONSTANT_NAME==NO` true olarak değerlendirilir (`0 == 0`), önyükleyicinin kodu deyimin `#elif` bölümünde (amaçlanan davranışın tam tersi) bırakmasını sağlar.

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
