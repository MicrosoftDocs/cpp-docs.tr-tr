---
title: Derleyici Hatası C3367 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3367
dev_langs:
- C++
helpviewer_keywords:
- C3367
ms.assetid: e675d42b-f5b0-4d43-aab1-1f5024233102
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2e063635e521efe1eabf8f2b50664ef8bf3e85e8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46020241"
---
# <a name="compiler-error-c3367"></a>Derleyici Hatası C3367

'static_member_function': statik işlev bağlanmamış bir temsilci oluşturmak için kullanamazsınız

Bağlanmamış bir temsilci çağırdığınızda, bir nesnenin örneğine geçirmeniz gerekir. Sınıf adı aracılığıyla bir statik üye işlevi çağrılan olduğundan, yalnızca bir örnek üyesi işlevi ile bağlanmamış bir temsilci örneğini oluşturabilir.

İlişkisiz temsilciler hakkında daha fazla bilgi için bkz: [nasıl yapılır: tanımlayın ve kullanım temsilciler (C + +/ CLI)](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md).

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