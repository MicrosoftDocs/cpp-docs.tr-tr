---
title: Derleyici hatası C2975
ms.date: 11/04/2016
f1_keywords:
- C2975
helpviewer_keywords:
- C2975
ms.assetid: 526f6b9d-6c76-4c12-9252-1b1d7c1e06c7
ms.openlocfilehash: 70fc648de8bcf4f1e85edf3a12cc0b7d3d70625f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201571"
---
# <a name="compiler-error-c2975"></a>Derleyici hatası C2975

> '*Argument*': '*Type*' için geçersiz şablon bağımsız değişkeni; derleme zamanı sabit ifadesi bekleniyor

Şablon bağımsız değişkeni şablon bildirimiyle eşleşmiyor; bir sabit ifade, açılı ayraç içinde görünmelidir. Gerçek şablon bağımsız değişkenleri olarak değişkenlere izin verilmez. Doğru türleri bulmak için şablon tanımını denetleyin.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2975 oluşturur ve ayrıca doğru kullanımı gösterir:

```cpp
// C2975.cpp
template<int I>
class X {};

int main() {
   int i = 4, j = 2;
   X<i + j> x1;   // C2975
   X<6> x2;   // OK
}
```

&#95; &#95;Ayrıca, [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)ile bir derleme&#95; &#95; zamanı sabiti olarak çizgi kullandığınızda da C2975 oluşur. Bir çözüm, **/Zi**yerine [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) ile derlenmelidir.

```cpp
// C2975b.cpp
// compile with: /ZI
// processor: x86
template<long line>
void test(void) {}

int main() {
   test<__LINE__>();   // C2975
}
```
