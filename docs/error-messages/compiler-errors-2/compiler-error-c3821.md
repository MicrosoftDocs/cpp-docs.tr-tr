---
title: Derleyici Hatası C3821
ms.date: 11/04/2016
f1_keywords:
- C3821
helpviewer_keywords:
- C3821
ms.assetid: 2b327c7a-5faf-443c-ae82-944fae25b4df
ms.openlocfilehash: 1cfc762cc7151eb2d55f8bd681bec935aea2acd4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50625972"
---
# <a name="compiler-error-c3821"></a>Derleyici Hatası C3821

'function': yönetilen tür veya işlev yönetilmeyen bir işlev içinde kullanılamaz

Satır içi derlemeyle işlevler veya [setjmp](../../c-runtime-library/reference/setjmp.md) değer türleri veya yönetilen sınıflar içeremez. Bu hatayı düzeltmek için satır içi derleme kaldırın ve `setjmp` yönetilen nesnelerini veya kaldırın.

Otomatik depolama vararg işlevinde kullanmayı denerseniz C3821 da meydana gelebilir.  Daha fazla bilgi için [değişken bağımsız değişken listeleri (...) (C + +/ CLI) ](../../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md) ve [başvuru türleri için C++ yığın anlamları](../../dotnet/cpp-stack-semantics-for-reference-types.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3821 oluşturur.

```
// C3821a.cpp
// compile with: /clr /c
public ref struct R {};
void test1(...) {
   R r;   // C3821
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3821 oluşturur.

```
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
