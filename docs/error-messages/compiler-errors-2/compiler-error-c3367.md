---
title: Derleyici hatası C3367
ms.date: 11/04/2016
f1_keywords:
- C3367
helpviewer_keywords:
- C3367
ms.assetid: e675d42b-f5b0-4d43-aab1-1f5024233102
ms.openlocfilehash: bedc94039f8621a93672c0dfa0cad5a54aad796e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201168"
---
# <a name="compiler-error-c3367"></a>Derleyici hatası C3367

' static_member_function ': ilişkisiz bir temsilci oluşturmak için statik işlev kullanılamaz

İlişkisiz bir temsilciyi çağırdığınızda, bir nesnenin örneğini geçirmeniz gerekir. Statik bir üye işlevi sınıf adı aracılığıyla çağrıldığı için, yalnızca bir örnek üye işlevi ile ilişkisiz bir temsilci örnekleyebilirsiniz.

İlişkisiz Temsilciler hakkında daha fazla bilgi için bkz. [nasıl yapılır: tanımlama ve kullanma temsilcileriC++(/CLI)](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md).

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
