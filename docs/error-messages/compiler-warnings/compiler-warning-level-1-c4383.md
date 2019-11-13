---
title: Derleyici Uyarısı (düzey 1) C4383
ms.date: 11/04/2016
f1_keywords:
- C4383
helpviewer_keywords:
- C4383
ms.assetid: 96c0e52d-874e-4b57-a154-0e49b6a00fae
ms.openlocfilehash: 9681408841173bad4aca3305e727ddde6cd98f14
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966167"
---
# <a name="compiler-warning-level-1-c4383"></a>Derleyici Uyarısı (düzey 1) C4383

' instance_dereference_operator ': bir tanıtıcının başvurusunun kaldırılması anlamı, Kullanıcı tanımlı ' operator ' işleci olduğunda değişebilir; işleneni açık olacak şekilde işleci statik bir işlev olarak yazın

Yönetilen bir türdeki başvuru işlecinin Kullanıcı tanımlı örnek geçersiz kılmayı eklediğinizde, türün başvuru işlecinin tanıtıcının nesnesini döndürme özelliğini geçersiz kılarsınız. Statik, Kullanıcı tanımlı bir başvuru operatörü yazmayı düşünün.

Daha fazla bilgi için, bkz. [nesne işleci (^)](../../extensions/handle-to-object-operator-hat-cpp-component-extensions.md) ve [izleme başvurusu işleci](../../extensions/tracking-reference-operator-cpp-component-extensions.md).

Ayrıca, bir örnek operatörü başvurulan meta veriler aracılığıyla diğer dil derleyicileri için kullanılamaz. Daha fazla bilgi için bkz. [Kullanıcı tanımlı işleçler (C++/CLI)](../../dotnet/user-defined-operators-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C4383 oluşturur.

```cpp
// C4383.cpp
// compile with: /clr /W1

ref struct S {
   int operator*() { return 0; }   // C4383
};

ref struct T {
   static int operator*(T%) { return 0; }
};

int main() {
   S s;
   S^ pS = %s;

   T t;
   T^ pT = %t;
   T% rT = *pT;
}
```