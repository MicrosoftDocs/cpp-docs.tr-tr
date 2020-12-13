---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3628'
title: Derleyici hatası C3628
ms.date: 11/04/2016
f1_keywords:
- C3628
helpviewer_keywords:
- C3628
ms.assetid: 0ff5a4a4-fcc9-47a0-a4d8-8af9cf2815f6
ms.openlocfilehash: ed0c434a40e6c513580e37b5fb2fc9f44b1dc5dc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144410"
---
# <a name="compiler-error-c3628"></a>Derleyici hatası C3628

' temel sınıf ': yönetilen veya WinRTclasses yalnızca genel devralmayı destekler

Yönetilen veya WinRT sınıfı [özel](../../cpp/private-cpp.md) veya [korumalı](../../cpp/protected-cpp.md) bir temel sınıf olarak kullanılmaya çalışıldı. Yönetilen veya WinRT sınıfı, yalnızca [ortak](../../cpp/public-cpp.md) erişime sahip bir temel sınıf olarak kullanılabilir.

Aşağıdaki örnek C3628 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
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
