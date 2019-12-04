---
title: Derleyici hatası C2256
ms.date: 11/04/2016
f1_keywords:
- C2256
helpviewer_keywords:
- C2256
ms.assetid: 171fa2bc-8c72-49cd-afe5-d723b7acd3c5
ms.openlocfilehash: b362a236953701278c57d2b738a6303e83b7637c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758820"
---
# <a name="compiler-error-c2256"></a>Derleyici hatası C2256

' function ' üzerinde Friend belirticisinin geçersiz kullanımı

Yıkıcı veya Oluşturucu [arkadaş](../../cpp/friend-cpp.md)olarak belirtilemez.

Aşağıdaki örnek C2256 oluşturur:

```cpp
// C2256.cpp
// compile with: /c
class C {
public:
   friend ~C();   // C2256
   ~C();   // OK
};
```
