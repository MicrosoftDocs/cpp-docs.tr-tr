---
title: Derleyici Hatası C2897 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2897
dev_langs:
- C++
helpviewer_keywords:
- C2897
ms.assetid: a88349e2-823f-42a0-8660-0653b677afa4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2d05663b913a3e310c091b62a81483f28bbf2c09
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049838"
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