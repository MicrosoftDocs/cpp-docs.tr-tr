---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2871'
title: Derleyici hatası C2871
ms.date: 11/04/2016
f1_keywords:
- C2871
helpviewer_keywords:
- C2871
ms.assetid: 44aeb84d-61f0-45e0-8dad-22a3cd46b7f8
ms.openlocfilehash: 6b62d5decb67cf6f8bad4d9b30123ccab54f51c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198303"
---
# <a name="compiler-error-c2871"></a>Derleyici hatası C2871

' name ': Bu ada sahip bir ad alanı yok

Bu hata, bir [using](../../cpp/namespaces-cpp.md#using_directives) yönergesine isim uzayı olmayan bir tanımlayıcıyı geçirdiğinizde oluşur.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2871 oluşturur:

```cpp
// C2871.cpp
// compile with: /c
namespace a {
   int fn(int i) { return i; }
}
namespace b {
   using namespace d;   // C2871 because d is not a namespace
   using namespace a;   // OK
}
```
