---
title: Derleyici Hatası C3842 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3842
dev_langs:
- C++
helpviewer_keywords:
- C3842
ms.assetid: 41a1a44a-c618-40a2-8d26-7da27d14095d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8db69ce3af28ed5878c43775b2c33542e5c817d6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055534"
---
# <a name="compiler-error-c3842"></a>Derleyici Hatası C3842

'function': WinRT yönetilen tür veya üye işlevlerinde 'const' ve 'volatile' niteleyicileri desteklenmiyor

[const](../../cpp/const-cpp.md) ve [geçici](../../cpp/volatile-cpp.md) Windows çalışma zamanı yönetilen tür veya üye işlevleri desteklenmez.

Aşağıdaki örnek, C3842 oluşturur:

```
// C3842a.cpp
// compile with: /clr /c
public ref struct A {
   void f() const {}   // C3842
   void f() volatile {}   // C3842

   void f() {}
};
```