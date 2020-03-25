---
title: Derleyici Uyarısı (düzey 3) C4686
ms.date: 08/27/2018
f1_keywords:
- C4686
helpviewer_keywords:
- C4686
ms.assetid: 767c83c2-9e4b-4f9e-88c8-02128ba563f4
ms.openlocfilehash: a8eae1ddeb875d267b82c67e989cb41e8c9b2afb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185457"
---
# <a name="compiler-warning-level-3-c4686"></a>Derleyici Uyarısı (düzey 3) C4686

> '*Kullanıcı tanımlı tür*': davranıştaki olası DEĞIŞIKLIK, udt dönüş çağırma kuralına göre değişiklik

## <a name="remarks"></a>Açıklamalar

Bir sınıf şablonu özelleştirmesi bir dönüş türünde kullanılmadan önce tanımlı değil. Sınıfı örnekleyen herhangi bir şey, C4686 çözümleyebilir; bir örneği bildirme veya bir üyeye erişme (C\<int >:: her şey) de seçenekleridir.

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

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
