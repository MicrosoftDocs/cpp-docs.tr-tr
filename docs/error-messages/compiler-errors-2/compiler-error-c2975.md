---
title: "Derleyici Hatası C2975 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2975
dev_langs: C++
helpviewer_keywords: C2975
ms.assetid: 526f6b9d-6c76-4c12-9252-1b1d7c1e06c7
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 65644cc13629481941ffdd8676e51311c665f106
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="compiler-error-c2975"></a>Derleyici Hatası C2975

> '*bağımsız değişkeni*': Geçersiz şablon bağımsız değişken için '*türü*', derleme zamanı sabit ifade bekleniyordu

Şablon bağımsız değişken şablon bildiriminde; eşleşmiyor bir sabit ifadesine açılı ayraçları içinde görünmesi gerekir. Şablon gerçek bağımsız değişkenler olarak değişkenlere izin verilmiyor. Doğru türlerini bulmak için şablon tanımını denetleyin.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2975 oluşturur ve ayrıca doğru kullanımını gösterir:

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

C2975 de oluşur kullandığınızda &#95; &#95; Çizgi &#95; &#95; derleme zamanı sabit ile olarak [/zı](../../build/reference/z7-zi-zi-debug-information-format.md). Bir çözümü ile derlemek için olacaktır [/zı](../../build/reference/z7-zi-zi-debug-information-format.md) yerine **/zı**.

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