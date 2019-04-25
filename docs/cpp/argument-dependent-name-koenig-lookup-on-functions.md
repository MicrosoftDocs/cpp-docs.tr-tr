---
title: İşlevlerde Bağımsız Değişkene Bağlı Ad (Koenig) Arama
ms.date: 11/04/2016
helpviewer_keywords:
- Koenig lookup
- argument-dependent lookup [C++]
ms.assetid: c0928401-da2c-4658-942d-9ba4df149c35
ms.openlocfilehash: d979b79c0f712ed35a42a44047dd1091010c72bf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62184486"
---
# <a name="argument-dependent-name-koenig-lookup-on-functions"></a>İşlevlerde Bağımsız Değişkene Bağlı Ad (Koenig) Arama

Derleyici bağımsız değişkene bağlı ad arama, nitelenmemiş bir işleve tanımını bulmak için kullanabilirsiniz. Bağımsız değişkene bağlı ad arama, Koenig araması olarak da adlandırılır. Bir işlev çağrısındaki her bağımsız değişken türünü hiyerarşisini ad alanları, sınıflar, yapılar, birleşimler veya şablonları içinde tanımlanır. Nitelenmemiş bir belirttiğinizde [sonek](../cpp/postfix-expressions.md) işlev çağrısı, derleyici her bağımsız değişken türü ile ilişkilendirilmiş hiyerarşi işlev tanımında arar.

## <a name="example"></a>Örnek

Bu örnekte, bu işlevi derleyici notları `f()` bir bağımsız değişken `x`. Bağımsız değişken `x` türünde `A::X`, ad alanında tanımlı `A`. Derleyici, ad alanı arar `A` ve işlevi için bir tanım bulduğunda `f()` türünde bir bağımsız değişken almayan `A::X`.

```cpp
// argument_dependent_name_koenig_lookup_on_functions.cpp
namespace A
{
   struct X
   {
   };
   void f(const X&)
   {
   }
}
int main()
{
// The compiler finds A::f() in namespace A, which is where
// the type of argument x is defined. The type of x is A::X.
   A::X x;
   f(x);
}
```