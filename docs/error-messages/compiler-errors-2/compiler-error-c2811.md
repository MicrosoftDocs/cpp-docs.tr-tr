---
title: Derleyici Hatası C2811 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2811
dev_langs:
- C++
helpviewer_keywords:
- C2811
ms.assetid: 6a44b18e-44c1-49d8-9b99-e0545b9a6e7d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e7e3b2d7bb76989b2028846efee6b18d10e1b0ad
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46059621"
---
# <a name="compiler-error-c2811"></a>Derleyici Hatası C2811

'type1': ref 'type2' devralınamıyor çünkü sınıf yalnızca devralınan bir başvuru sınıfı veya arabirim sınıfı

Yönetilmeyen bir sınıf, yönetilen bir sınıf için temel sınıf olarak kullanma girişimi.

Aşağıdaki örnek, C2811 oluşturur:

```
// C2811.cpp
// compile with: /clr /c
struct S{};
ref struct T {};
ref class C : public S {};   // C2811
ref class D : public T {};   // OK
```