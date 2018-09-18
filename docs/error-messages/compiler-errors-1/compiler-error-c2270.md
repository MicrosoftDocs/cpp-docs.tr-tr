---
title: Derleyici Hatası C2270 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2270
dev_langs:
- C++
helpviewer_keywords:
- C2270
ms.assetid: b52c068e-0b61-42e7-b775-4d57b3ddcba0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cb1c6d1028f5ea2a34693a5098a7a869f2ff80ef
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036936"
---
# <a name="compiler-error-c2270"></a>Derleyici Hatası C2270

'function': üye olmayan işlevlerde değiştiricilere izin verilmez

İle bildirilen bir değiştiricilere işlevi [const](../../cpp/const-cpp.md), [geçici](../../cpp/volatile-cpp.md), veya başka bir bellek modeli değiştiricisi.

Aşağıdaki örnek, C2270 oluşturur:

```
// C2270.cpp
// compile with: /c
void func1(void) const;   // C2270, nonmember function

void func2(void);

class CMyClass {
public:
   void func2(void) const;
};
```