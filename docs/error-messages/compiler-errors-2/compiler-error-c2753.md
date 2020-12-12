---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2753'
title: Derleyici hatası C2753
ms.date: 11/04/2016
f1_keywords:
- C2753
helpviewer_keywords:
- C2753
ms.assetid: 92bfeeac-524a-4a8e-9a4f-fb8269055826
ms.openlocfilehash: d7888086f81f26092d41be440f75ef60400229ee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174409"
---
# <a name="compiler-error-c2753"></a>Derleyici hatası C2753

'*Template*': kısmi özelleştirme birincil şablonun bağımsız değişken listesiyle eşleşemez

Şablon bağımsız değişken listesi parametre listesiyle eşleşiyorsa, derleyici onu aynı şablon olarak değerlendirir. Aynı şablonu iki kez tanımlamaya izin verilmez.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2753 oluşturur ve bunu çözmek için bir yol gösterir:

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
