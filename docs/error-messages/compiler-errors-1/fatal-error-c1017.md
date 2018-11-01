---
title: Önemli hata C1017
ms.date: 11/04/2016
f1_keywords:
- C1017
helpviewer_keywords:
- C1017
ms.assetid: 5542e604-599d-4e36-8f83-1d454c5753c9
ms.openlocfilehash: e2309b93be65b049c35abf96572e144a0a518007
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50614285"
---
# <a name="fatal-error-c1017"></a>Önemli hata C1017

Geçersiz tamsayı sabit ifadesi

İfade bir `#if` yönergesi yoktu veya bir sabite sonucu vermedi.

Sabitler kullanılarak tanımlanan `#define` olarak kullanılıyorsa, bir tamsayı sabit değerleri içermelidir bir `#if`, `#elif`, veya `#else` yönergesi.

Aşağıdaki örnek, C1017 oluşturur:

```
// C1017.cpp
#define CONSTANT_NAME "YES"
#if CONSTANT_NAME   // C1017
#endif
```

Olası çözüm:

```
// C1017b.cpp
// compile with: /c
#define CONSTANT_NAME 1
#if CONSTANT_NAME
#endif
```

Çünkü `CONSTANT_NAME` bir dize ve tamsayı değil, değerlendirir `#if` yönergesi önemli hata C1017 oluşturur.

Diğer durumlarda, önişlemci tanımlanmamış bir sabit değer sıfır olarak değerlendirir. Aşağıdaki örnekte gösterildiği gibi bu istenmeyen sonuçlara neden olabilir. `YES` sıfır olarak değerlendirilen bu nedenle, tanımsızdır. İfade `#if` `CONSTANT_NAME` yanlış ve kod, kullanılacak veren `YES` önişlemci tarafından kaldırılır. `NO` Ayrıca tanımlanmamış (sıfır), bu nedenle olan `#elif` `CONSTANT_NAME==NO` true olarak değerlendirilen (`0 == 0`), kodda bırakmak önişlemci neden `#elif` deyiminin bölümü — amaçlanan bir davranış tam tersidir.

```
// C1017c.cpp
// compile with: /c
#define CONSTANT_NAME YES
#if CONSTANT_NAME
   // Code to use on YES...
#elif CONSTANT_NAME==NO
   // Code to use on NO...
#endif
```

Tam olarak derleyici önişlemci yönergeleri nasıl işlediğini görmek için [/P](../../build/reference/p-preprocess-to-a-file.md), [/E](../../build/reference/e-preprocess-to-stdout.md), veya [/EP](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md).