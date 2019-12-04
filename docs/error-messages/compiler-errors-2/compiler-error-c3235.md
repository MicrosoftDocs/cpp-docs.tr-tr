---
title: Derleyici hatası C3235
ms.date: 11/04/2016
f1_keywords:
- C3235
helpviewer_keywords:
- C3235
ms.assetid: 0554d6c7-e1dc-4c99-8934-cbcf491c8203
ms.openlocfilehash: e284cf0d7742e60ceb5d381777ac68e9d0ea89be
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759405"
---
# <a name="compiler-error-c3235"></a>Derleyici hatası C3235

' özelleşme ': bir genel sınıfın açık veya kısmi özelleştirmesine izin verilmiyor

Genel sınıflar açık veya kısmi uzmanlık için kullanılamaz.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3235 oluşturur.

```cpp
// C3235.cpp
// compile with: /clr
generic<class T>
public ref class C {};

generic<>
public ref class C<int> {};   // C3235 Remove this specialization to resolve this error.
```
