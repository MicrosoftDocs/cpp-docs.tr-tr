---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2979'
title: Derleyici hatası C2979
ms.date: 11/04/2016
f1_keywords:
- C2979
helpviewer_keywords:
- C2979
ms.assetid: 98bd9043-ec44-451e-a482-3a8e35fc7464
ms.openlocfilehash: 2c57c1345c359732f46220e7430b1a8b5092a17b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189450"
---
# <a name="compiler-error-c2979"></a>Derleyici hatası C2979

genel türlerde açık uzmanlık desteklenmez

Genel bir sınıf yanlış olarak bildirildi.  Daha fazla bilgi için bkz. [Genel türler](../../extensions/generics-cpp-component-extensions.md) .

## <a name="example"></a>Örnek

Aşağıdaki örnek C2979 oluşturur.

```cpp
// C2979.cpp
// compile with: /clr /c
generic <>
ref class Utils {};   // C2979 error

generic <class T>
ref class Utils2 {};   // OK
```
