---
title: Derleyici Hatası C3367
ms.date: 11/04/2016
f1_keywords:
- C3367
helpviewer_keywords:
- C3367
ms.assetid: e675d42b-f5b0-4d43-aab1-1f5024233102
ms.openlocfilehash: f53312fa9225270ef79d50d2ad351adce790d6fa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300543"
---
# <a name="compiler-error-c3367"></a>Derleyici Hatası C3367

'static_member_function': statik işlev bağlanmamış bir temsilci oluşturmak için kullanamazsınız

Bağlanmamış bir temsilci çağırdığınızda, bir nesnenin örneğine geçirmeniz gerekir. Sınıf adı aracılığıyla bir statik üye işlevi çağrılan olduğundan, yalnızca bir örnek üyesi işlevi ile bağlanmamış bir temsilci örneğini oluşturabilir.

İlişkisiz temsilciler hakkında daha fazla bilgi için bkz: [nasıl yapılır: Temsilcileri tanımlama ve kullanma (C++/CLI)](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3367 oluşturur.

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