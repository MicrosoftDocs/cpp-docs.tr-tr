---
title: Derleyici Hatası C2753
ms.date: 11/04/2016
f1_keywords:
- C2753
helpviewer_keywords:
- C2753
ms.assetid: 92bfeeac-524a-4a8e-9a4f-fb8269055826
ms.openlocfilehash: e13c45cec99e60d8aec7dcc3db8e5a4813ea7de9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62228789"
---
# <a name="compiler-error-c2753"></a>Derleyici Hatası C2753

'*şablon*': Kısmi özelleştirme birincil şablonun bağımsız değişken listesi eşleşemez

Derleyici şablon bağımsız değişken listesi parametre listesi eşleşirse, aynı şablon olarak değerlendirir. İki kez aynı şablon tanımlama izin verilmez.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2753 oluşturur ve bunu düzeltmek için bir yol gösterir:

```cpp
// C2753.cpp
// compile with: cl /c C2753.cpp
template<class T>
struct A {};

template<class T>
struct A<T> {};   // C2753
// try the following line instead
// struct A<int> {};

template<class T, class U, class V, class W, class X>
struct B {};
```