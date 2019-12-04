---
title: Derleyici hatası C2161
ms.date: 11/04/2016
f1_keywords:
- C2161
helpviewer_keywords:
- C2161
ms.assetid: d6798821-13bb-4e60-924f-85f7bf955387
ms.openlocfilehash: dd75fb4ba035f21a71fff1f345c0c397415bc0ec
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758430"
---
# <a name="compiler-error-c2161"></a>Derleyici hatası C2161

' # # ' makro tanımının sonunda oluşamaz

Makro tanımı, belirteç yapıştırma işleci (# #) ile sonlandı.

Aşağıdaki örnek C2161 oluşturur:

```cpp
// C2161.cpp
// compile with: /c
#define mac(a,b) a   // OK
#define mac(a,b) a##   // C2161
```
