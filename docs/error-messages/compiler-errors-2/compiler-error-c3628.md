---
title: Derleyici Hatası C3628
ms.date: 11/04/2016
f1_keywords:
- C3628
helpviewer_keywords:
- C3628
ms.assetid: 0ff5a4a4-fcc9-47a0-a4d8-8af9cf2815f6
ms.openlocfilehash: 581aae7e1f979b3dd39caf2ce3d263fdb856c56a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62221691"
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
