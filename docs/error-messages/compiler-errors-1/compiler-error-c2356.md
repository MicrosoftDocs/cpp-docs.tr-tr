---
title: Derleyici Hatası C2356 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2356
dev_langs:
- C++
helpviewer_keywords:
- C2356
ms.assetid: 84d5a816-9a61-4d45-9978-38e485bbf767
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8dfad1703b36e1cd995207d35b99b323c883f828
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065419"
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