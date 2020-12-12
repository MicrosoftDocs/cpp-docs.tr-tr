---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3821'
title: Derleyici hatası C3821
ms.date: 11/04/2016
f1_keywords:
- C3821
helpviewer_keywords:
- C3821
ms.assetid: 2b327c7a-5faf-443c-ae82-944fae25b4df
ms.openlocfilehash: 745efeb21933e06f65f9e700ad5780da8234da90
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249379"
---
# <a name="compiler-error-c3821"></a>Derleyici hatası C3821

' function ': yönetilen tür veya işlev yönetilmeyen bir işlevde kullanılamaz

Satır içi derleme veya [setjmp](../../c-runtime-library/reference/setjmp.md) içeren işlevler değer türleri veya yönetilen sınıflar içeremez. Bu hatayı onarmak için, satır içi derlemeyi kaldırın ve `setjmp` veya yönetilen nesneleri kaldırın.

C3821, bir vararg işlevinde otomatik depolamayı kullanmayı denerseniz da oluşabilir.  Daha fazla bilgi için bkz. [başvuru türleri Için](../../dotnet/cpp-stack-semantics-for-reference-types.md) [değişken bağımsız değişken listeleri (...) (c++/CLI)](../../extensions/variable-argument-lists-dot-dot-dot-cpp-cli.md) ve c++ yığın semantiği.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek C3821 oluşturur.

```cpp
// C3821a.cpp
// compile with: /clr /c
public ref struct R {};
void test1(...) {
   R r;   // C3821
}
```

Aşağıdaki örnek C3821 oluşturur.

```cpp
// C3821b.cpp
// compile with: /clr
// processor: /x86
ref class A {
   public:
   int i;
};

int main() {
   // cannot use managed classes in this function
   A ^a;

   __asm {
      nop
   }
} // C3821
```
