---
title: Derleyici Hatası C2979 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2979
dev_langs:
- C++
helpviewer_keywords:
- C2979
ms.assetid: 98bd9043-ec44-451e-a482-3a8e35fc7464
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 66f43af14474c042d7a4a311bbe672394a2f2d1d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053355"
---
# <a name="compiler-error-c2979"></a>Derleyici Hatası C2979

Açık uzmanlık'nda genel türler için desteklenmez.

Genel sınıf yanlış bildirildi.  Bkz: [genel türler](../../windows/generics-cpp-component-extensions.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2979 oluşturur.

```
// C2979.cpp
// compile with: /clr /c
generic <>
ref class Utils {};   // C2979 error

generic <class T>
ref class Utils2 {};   // OK
```