---
title: Derleyici Hatası C2356
ms.date: 11/04/2016
f1_keywords:
- C2356
helpviewer_keywords:
- C2356
ms.assetid: 84d5a816-9a61-4d45-9978-38e485bbf767
ms.openlocfilehash: 0166cce6011017b8a18821666083f7c47f58b7a9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302546"
---
# <a name="compiler-error-c2356"></a>Derleyici Hatası C2356

başlatma kesiminin çeviri birimi sırasında değiştirmemelidir

Olası nedenler:

- `#pragma init_seg` Segmenti başlatma kodu tarafından öncesinde

- `#pragma init_seg` bir başkası tarafından öncesinde `#pragma init_seg`

Çözmek için segment başlatma kodu modülü başlangıcına Taşı. Birden fazla alana başlatılması gerekir, bunları modüller ayrı taşıyın.

Aşağıdaki örnek, C2356 oluşturur:

```
// C2356.cpp
#pragma warning(disable : 4075)

int __cdecl myexit(void (__cdecl *)());
int __cdecl myexit2(void (__cdecl *)());

#pragma init_seg(".mine$m",myexit)
#pragma init_seg(".mine$m",myexit2)   // C2356
```