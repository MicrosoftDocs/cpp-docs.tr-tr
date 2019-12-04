---
title: Derleyici hatası C2897
ms.date: 11/04/2016
f1_keywords:
- C2897
helpviewer_keywords:
- C2897
ms.assetid: a88349e2-823f-42a0-8660-0653b677afa4
ms.openlocfilehash: 1433faade0a41ad8b63a3b40cb5d02f724bde658
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760780"
---
# <a name="compiler-error-c2897"></a>Derleyici hatası C2897

yıkıcı/Sonlandırıcı bir işlev şablonu olamaz

Yok ediciler veya sonlandırıcılar aşırı yüklenemez, bu nedenle bir yok edicinin şablon olarak bildirilmesi (bir yıkıcı kümesi tanımlar) izin verilmez.

Aşağıdaki örnek C2897 oluşturur:

## <a name="example"></a>Örnek

Aşağıdaki örnek C2897 oluşturur.

```cpp
// C2897.cpp
// compile with: /c
class X {
public:
   template<typename T> ~X() {}   // C2897
};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek C2897 oluşturur.

```cpp
// C2897_b.cpp
// compile with: /c /clr
ref struct R2 {
protected:
   template<typename T> !R2(){}   // C2897 error
};
```
