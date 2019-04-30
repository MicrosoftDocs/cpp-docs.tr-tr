---
title: Derleyici Hatası C2897
ms.date: 11/04/2016
f1_keywords:
- C2897
helpviewer_keywords:
- C2897
ms.assetid: a88349e2-823f-42a0-8660-0653b677afa4
ms.openlocfilehash: 264ad52a10c6cf19d1105561f1140cf2d3e2f8e6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378849"
---
# <a name="compiler-error-c2897"></a>Derleyici Hatası C2897

bir yok edici/Sonlandırıcı bir işlev şablonu olamaz

(Bu yok ediciler kümesi tanımlarsınız) bir şablon olarak bir yıkıcı bildirmek izin için yıkıcı veya Sonlandırıcı, aşırı yüklenemez.

Aşağıdaki örnek, C2897 oluşturur:

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2897 oluşturur.

```
// C2897.cpp
// compile with: /c
class X {
public:
   template<typename T> ~X() {}   // C2897
};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2897 oluşturur.

```
// C2897_b.cpp
// compile with: /c /clr
ref struct R2 {
protected:
   template<typename T> !R2(){}   // C2897 error
};
```