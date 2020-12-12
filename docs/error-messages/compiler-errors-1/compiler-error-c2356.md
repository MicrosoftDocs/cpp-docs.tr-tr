---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2356'
title: Derleyici hatası C2356
ms.date: 11/04/2016
f1_keywords:
- C2356
helpviewer_keywords:
- C2356
ms.assetid: 84d5a816-9a61-4d45-9978-38e485bbf767
ms.openlocfilehash: c0e2d179bb41e6cbae674d92976674ab90f05c0f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328328"
---
# <a name="compiler-error-c2356"></a>Derleyici hatası C2356

başlatma segmenti çeviri birimi sırasında değişmemelidir

Olası nedenler:

- `#pragma init_seg` önünde segment başlatma kodu

- `#pragma init_seg` önce başka bir `#pragma init_seg`

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
