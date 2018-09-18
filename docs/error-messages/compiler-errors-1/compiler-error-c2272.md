---
title: Derleyici Hatası C2272 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2272
dev_langs:
- C++
helpviewer_keywords:
- C2272
ms.assetid: 1517706a-9c27-452e-9b10-3424b3d232bc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e17765ee0acbf20d76e631bf7fccfb3413c5dc1d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46040316"
---
# <a name="compiler-error-c2272"></a>Derleyici Hatası C2272

'function': statik üye işlevlerinde izin verilmez

A `static` üye işlevi bildirilmiş bir bellek-model tanımlayıcısı ile gibi [const](../../cpp/const-cpp.md) veya [geçici](../../cpp/volatile-cpp.md), ve bu tür değiştiricilere izin verilmez `static` üye işlevleri.

Aşağıdaki örnek, C2272 oluşturur:

```
// C2272.cpp
// compile with: /c
class CMyClass {
public:
   static void func1() const volatile;   // C2272  func1 is static
   void func2() const volatile;   // OK
};
```