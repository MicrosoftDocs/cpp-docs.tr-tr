---
description: 'Daha fazla bilgi edinin: Işlevlerde Argument-Dependent adı (KOENIG) arama'
title: İşlevlerde Bağımsız Değişkene Bağlı Ad (Koenig) Arama
ms.date: 11/04/2016
helpviewer_keywords:
- Koenig lookup
- argument-dependent lookup [C++]
ms.assetid: c0928401-da2c-4658-942d-9ba4df149c35
ms.openlocfilehash: 726174041c919a2918687101b223f0e1cca3d5ed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97288197"
---
# <a name="argument-dependent-name-koenig-lookup-on-functions"></a>İşlevlerde Bağımsız Değişkene Bağlı Ad (Koenig) Arama

Derleyici, bağımsız değişkene bağlı ad aramasını, nitelenmemiş bir işlev çağrısının tanımını bulmak için kullanabilir. Bağımsız değişkene bağlı ad aramasına, KOENIG araması da denir. Bir işlev çağrısındaki her bağımsız değişkenin türü bir ad alanı, sınıf, yapı, birleşim veya şablon hiyerarşisi içinde tanımlanır. Nitelenmemiş bir [sonek](../cpp/postfix-expressions.md) işlev çağrısı belirttiğinizde, derleyici her bağımsız değişken türüyle ilişkili hiyerarşide işlev tanımını arar.

## <a name="example"></a>Örnek

Örnekte, derleyici bu işlevin `f()` bir bağımsız değişken aldığını Not alır `x` . Bağımsız değişken `x` `A::X` , ad alanında tanımlanan türdür `A` . Derleyici ad alanını arar `A` ve `f()` türünde bir bağımsız değişken alan bir işlev tanımı bulur `A::X` .

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
