---
title: Derleyici hatası C2356
ms.date: 11/04/2016
f1_keywords:
- C2356
helpviewer_keywords:
- C2356
ms.assetid: 84d5a816-9a61-4d45-9978-38e485bbf767
ms.openlocfilehash: e306c5a8f9175bc3c7902b20263aa2e451944182
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759938"
---
# <a name="compiler-error-c2356"></a>Derleyici hatası C2356

başlatma segmenti çeviri birimi sırasında değişmemelidir

Olası nedenler:

- `#pragma init_seg` önünde segment başlatma kodu

- daha önce başka bir `#pragma init_seg` `#pragma init_seg`

Çözümlemek için, segment başlatma kodunu modülün başına taşıyın. Birden çok alan başlatılması gerekiyorsa onları ayrı modüllere taşıyın.

Aşağıdaki örnek C2356 oluşturur:

```cpp
// C2356.cpp
#pragma warning(disable : 4075)

int __cdecl myexit(void (__cdecl *)());
int __cdecl myexit2(void (__cdecl *)());

#pragma init_seg(".mine$m",myexit)
#pragma init_seg(".mine$m",myexit2)   // C2356
```
