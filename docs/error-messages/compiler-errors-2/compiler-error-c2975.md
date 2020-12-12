---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2975'
title: Derleyici hatası C2975
ms.date: 11/04/2016
f1_keywords:
- C2975
helpviewer_keywords:
- C2975
ms.assetid: 526f6b9d-6c76-4c12-9252-1b1d7c1e06c7
ms.openlocfilehash: 9f9108d1dc4e0fe61b6dd2135fb69bbaedfaedf0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210354"
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

C2975 Ayrıca, [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)ile derleme zamanı sabiti olarak &#95;&#95;satırı&#95;&#95; kullandığınızda da oluşur. Bir çözüm, **/Zi** yerine [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) ile derlenmelidir.

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
