---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3268'
title: Derleyici hatası C3268
ms.date: 11/04/2016
f1_keywords:
- C3268
helpviewer_keywords:
- C3268
ms.assetid: d74a630c-daea-4e29-9759-83efef7fb184
ms.openlocfilehash: 405977afe5a58545dd5e8b0d54cb08f431935191
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223327"
---
# <a name="compiler-error-c3268"></a>Derleyici hatası C3268

> '*Function*': bir genel işlev veya bir genel sınıfın üye işlevi bir değişken parametre listesine sahip olamaz

## <a name="remarks"></a>Açıklamalar

**/Clr: Pure** ve **/clr: Safe** derleyici seçenekleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ' de desteklenmez.

Daha fazla bilgi için bkz. [Genel türler](../../extensions/generics-cpp-component-extensions.md) .

## <a name="example"></a>Örnek

Aşağıdaki örnek C3268 oluşturur.

```cpp
// C3268.cpp
// compile with: /clr:pure /c
generic <class ItemType>
void Test(ItemType item, ...) {}   // C3268
// try the following line instead
// void Test(ItemType item) {}

generic <class ItemType2>
ref struct MyStruct { void Test(...){} };   // C3268
// try the following line instead
// ref struct MyStruct { void Test2(){} };   // OK
```
