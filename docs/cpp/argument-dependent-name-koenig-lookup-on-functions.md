---
title: İşlevlerde Bağımsız Değişkene Bağlı Ad (Koenig) Arama
ms.date: 11/04/2016
helpviewer_keywords:
- Koenig lookup
- argument-dependent lookup [C++]
ms.assetid: c0928401-da2c-4658-942d-9ba4df149c35
ms.openlocfilehash: 88811e8070fdfe398bc12734221dee772515d8bc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190544"
---
# <a name="argument-dependent-name-koenig-lookup-on-functions"></a>İşlevlerde Bağımsız Değişkene Bağlı Ad (Koenig) Arama

Derleyici, bağımsız değişkene bağlı ad aramasını, nitelenmemiş bir işlev çağrısının tanımını bulmak için kullanabilir. Bağımsız değişkene bağlı ad aramasına, KOENIG araması da denir. Bir işlev çağrısındaki her bağımsız değişkenin türü bir ad alanı, sınıf, yapı, birleşim veya şablon hiyerarşisi içinde tanımlanır. Nitelenmemiş bir [sonek](../cpp/postfix-expressions.md) işlev çağrısı belirttiğinizde, derleyici her bağımsız değişken türüyle ilişkili hiyerarşide işlev tanımını arar.

## <a name="example"></a>Örnek

Örnekte, derleyici `f()` işlev `x`bir bağımsız değişken alır. Bağımsız değişken `x`, ad alanı `A`tanımlanmış `A::X`türüdür. Derleyici ad alanı `A` arar ve `A::X`türünde bir bağımsız değişken alan bir işlev `f()` tanımı bulur.

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
