---
title: Derleyici Hatası C3628 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3628
dev_langs:
- C++
helpviewer_keywords:
- C3628
ms.assetid: 0ff5a4a4-fcc9-47a0-a4d8-8af9cf2815f6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9a65dc33c5381b063c3adb01072e930075108649
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037378"
---
# <a name="compiler-error-c3628"></a>Derleyici Hatası C3628

'temel sınıfı': yönetilen veya WinRTclasses yalnızca ortak devralmayı destekler

Yönetilen veya WinRT kullanmak için bir girişimde bulunuldu olarak sınıf bir [özel](../../cpp/private-cpp.md) veya [korumalı](../../cpp/protected-cpp.md) temel sınıfı. Yönetilen veya WinRT sınıfı yalnızca kullanılabilir sahip bir temel sınıf olarak [genel](../../cpp/public-cpp.md) erişim.

Aşağıdaki örnek, C3628 oluşturur ve bu sorunun nasıl gösterir:

```
// C3628a.cpp
// compile with: /clr
ref class B {
};

ref class D : private B {   // C3628

// The following line resolves the error.
// ref class D : public B {
};

int main() {
}
```
