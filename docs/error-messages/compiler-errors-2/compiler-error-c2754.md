---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2754'
title: Derleyici hatası C2754
ms.date: 11/04/2016
f1_keywords:
- C2754
helpviewer_keywords:
- C2754
ms.assetid: 1cab66c5-da9d-4b81-b7fb-9cdc48ff1ccc
ms.openlocfilehash: 68840f85d7a7f9be18246dfa4f3176a76f0fb9ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336229"
---
# <a name="compiler-error-c2754"></a>Derleyici hatası C2754

' özelleşme ': kısmi özelleştirmede bağımlı bir tür olmayan şablon parametresi olamaz

Bağımlı tür olmayan bir şablon parametresine sahip bir şablon sınıfını kısmen özelleştirmek için bir girişimde bulunuldu. Buna izin verilmez.

Aşağıdaki örnek C2754 oluşturur:

```cpp
// C2754.cpp
// compile with: /c

template<class T, T t>
struct A {};

template<class T, int N>
struct B {};

template<class T> struct A<T,5> {};   // C2754
template<> struct A<int,5> {};   // OK
template<class T> struct B<T,5> {};   // OK
```
