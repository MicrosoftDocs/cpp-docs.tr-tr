---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2897'
title: Derleyici hatası C2897
ms.date: 11/04/2016
f1_keywords:
- C2897
helpviewer_keywords:
- C2897
ms.assetid: a88349e2-823f-42a0-8660-0653b677afa4
ms.openlocfilehash: b1a1f66987aa4bbd01fdf12f88f8933e3436938a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270881"
---
# <a name="compiler-error-c2897"></a>Derleyici hatası C2897

yıkıcı/Sonlandırıcı bir işlev şablonu olamaz

Yok ediciler veya sonlandırıcılar aşırı yüklenemez, bu nedenle bir yok edicinin şablon olarak bildirilmesi (bir yıkıcı kümesi tanımlar) izin verilmez.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek C2897 oluşturur.

```cpp
// C2897.cpp
// compile with: /c
class X {
public:
   template<typename T> ~X() {}   // C2897
};
```

Aşağıdaki örnek C2897 oluşturur.

```cpp
// C2897_b.cpp
// compile with: /c /clr
ref struct R2 {
protected:
   template<typename T> !R2(){}   // C2897 error
};
```
