---
title: Derleyici hatası C3821
ms.date: 11/04/2016
f1_keywords:
- C3821
helpviewer_keywords:
- C3821
ms.assetid: 2b327c7a-5faf-443c-ae82-944fae25b4df
ms.openlocfilehash: 25023277258d33ab77bde18f6cdfabc862f50a63
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74741748"
---
# <a name="compiler-error-c3821"></a>Derleyici hatası C3821

' function ': yönetilen tür veya işlev yönetilmeyen bir işlevde kullanılamaz

Satır içi derleme veya [setjmp](../../c-runtime-library/reference/setjmp.md) içeren işlevler değer türleri veya yönetilen sınıflar içeremez. Bu hatayı onarmak için, satır içi derlemeyi kaldırın ve `setjmp` veya yönetilen nesneleri kaldırın.

C3821, bir vararg işlevinde otomatik depolamayı kullanmayı denerseniz da oluşabilir.  Daha fazla bilgi için bkz. [ C++ başvuru türleri için](../../dotnet/cpp-stack-semantics-for-reference-types.md) [değişken bağımsız değişken listeleri (C++...) (/CLI)](../../extensions/variable-argument-lists-dot-dot-dot-cpp-cli.md) ve yığın semantiği.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3821 oluşturur.

```cpp
// C3821a.cpp
// compile with: /clr /c
public ref struct R {};
void test1(...) {
   R r;   // C3821
}
```

## <a name="example"></a>Örnek

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
