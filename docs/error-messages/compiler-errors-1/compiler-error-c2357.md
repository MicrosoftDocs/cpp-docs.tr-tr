---
title: Derleyici Hatası C2357 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2357
dev_langs:
- C++
helpviewer_keywords:
- C2357
ms.assetid: d1083945-0ea2-4385-9e66-8c665978806c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2d6468774947ed92630d0e10badc341c5841a5aa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46025444"
---
# <a name="compiler-error-c2357"></a>Derleyici Hatası C2357

'identifier': 'type' türünde bir işlev olmalıdır

Kodunuzu bir sürümünü bildirir `atexit` sürümü eşleşmiyor işlevi derleyici tarafından dahili olarak bildirilir. Bildirme `atexit` gibi:

```
int __cdecl atexit(void (__cdecl *)());
```

Daha fazla bilgi için [init_seg](../../preprocessor/init-seg.md).

Aşağıdaki örnek, C2357 oluşturur:

```
// C2357.cpp
// compile with: /c
// C2357 expected
#pragma warning(disable : 4075)
// Uncomment the following line to resolve.
// int __cdecl myexit(void (__cdecl *)());
#pragma init_seg(".mine$m",myexit)
```