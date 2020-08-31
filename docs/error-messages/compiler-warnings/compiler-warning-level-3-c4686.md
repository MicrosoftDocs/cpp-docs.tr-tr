---
title: Derleyici Uyarısı (düzey 3) C4686
description: Microsoft C++ derleyicisi uyarı C4686.
ms.date: 08/29/2020
f1_keywords:
- C4686
helpviewer_keywords:
- C4686
ms.assetid: 767c83c2-9e4b-4f9e-88c8-02128ba563f4
ms.openlocfilehash: 6886ae7f413de630457b53e85b5cd75c4542ee19
ms.sourcegitcommit: 3628707bc17c99aac7aac27eb126cc2eaa4d07b4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2020
ms.locfileid: "89194503"
---
# <a name="compiler-warning-level-3-c4686"></a>Derleyici Uyarısı (düzey 3) C4686

> '*Kullanıcı tanımlı tür*': davranıştaki olası DEĞIŞIKLIK, udt dönüş çağırma kuralına göre değişiklik

## <a name="remarks"></a>Açıklamalar

Bir sınıf şablonu özelleştirmesi, bir dönüş türünde kullanılmadan önce tanımlanmadı. Sınıfın örneğini oluşturan her şey C4686 çözümleniyor; bir örnek bildirmek veya bir üyeye erişmek (örneğin, `C<int>::some_member` ) de seçenekleridir.

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

## <a name="example"></a>Örnek

Bunun yerine aşağıdakileri deneyin:

```cpp
// C4686.cpp
// compile with: /W3
#pragma warning (default : 4686)
template <class T>
class C;

template <class T>
C<T> f(T);

template <class T>
class C {};

int main() {
   f(1);   // C4686
}

template <class T>
C<T> f(T) {
   return C<int>();
}
```
