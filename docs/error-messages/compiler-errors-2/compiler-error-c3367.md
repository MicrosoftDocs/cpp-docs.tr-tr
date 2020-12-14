---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3367'
title: Derleyici hatası C3367
ms.date: 11/04/2016
f1_keywords:
- C3367
helpviewer_keywords:
- C3367
ms.assetid: e675d42b-f5b0-4d43-aab1-1f5024233102
ms.openlocfilehash: cd428bb0472ab9cb621f85ac684cbb4d9bbc12d6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245284"
---
# <a name="compiler-error-c3367"></a>Derleyici hatası C3367

' static_member_function ': ilişkisiz bir temsilci oluşturmak için statik işlev kullanılamaz

İlişkisiz bir temsilciyi çağırdığınızda, bir nesnenin örneğini geçirmeniz gerekir. Statik bir üye işlevi sınıf adı aracılığıyla çağrıldığı için, yalnızca bir örnek üye işlevi ile ilişkisiz bir temsilci örnekleyebilirsiniz.

İlişkisiz Temsilciler hakkında daha fazla bilgi için bkz. [nasıl yapılır: temsilcileri tanımlama ve kullanma (C++/CLI)](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3367 oluşturur.

```cpp
// C3367.cpp
// compile with: /clr
ref struct R {
   void b() {}
   static void f() {}
};

delegate void Del(R^);

int main() {
   Del ^ a = gcnew Del(&R::b);   // OK
   Del ^ b = gcnew Del(&R::f);   // C3367
}
```
