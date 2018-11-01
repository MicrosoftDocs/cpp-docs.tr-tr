---
title: Derleyici Hatası C2975
ms.date: 11/04/2016
f1_keywords:
- C2975
helpviewer_keywords:
- C2975
ms.assetid: 526f6b9d-6c76-4c12-9252-1b1d7c1e06c7
ms.openlocfilehash: 66b7c0d61cbc8141b9ed3e5f6eb329b68eb00477
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50609761"
---
# <a name="compiler-error-c2975"></a>Derleyici Hatası C2975

> '*bağımsız değişken*': Geçersiz şablon bağımsız değişkeni için '*türü*', derleme zamanı sabit ifadesi bekleniyor

Şablon bağımsız değişkeni, şablon bildirimindeki eşleşmiyor; sabit bir ifade, açılı ayraçlar içinde görüntülenmesi gerekir. Şablon gerçek bağımsız değişkenlere izin verilmiyor. Doğru tür bulmak için şablon tanımı kontrol edin.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2975 oluşturur ve ayrıca doğru kullanımını gösterir:

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

C2975 de gerçekleşir kullandığınızda &#95; &#95;satırı&#95; &#95; ile bir derleme zamanı sabiti olarak [/zi](../../build/reference/z7-zi-zi-debug-information-format.md). Tek bir çözüm ile derlemek için olacak [/zi](../../build/reference/z7-zi-zi-debug-information-format.md) yerine **/zi**.

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