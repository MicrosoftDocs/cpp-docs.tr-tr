---
title: Derleyici hatası C2395
ms.date: 11/04/2016
f1_keywords:
- C2395
helpviewer_keywords:
- C2395
ms.assetid: 2d9e3b28-8c2c-4f41-a57f-61ef88fc2af0
ms.openlocfilehash: 2ac59856770b04dd3c4ea14360e0a83dd99f2150
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744946"
---
# <a name="compiler-error-c2395"></a>Derleyici hatası C2395

' your_type:: operator'op ' ': CLR veya WinRT işleci geçerli değil. En az bir parametre şu türlerde olmalıdır: 'T ', 'T% ', 'T & ', 'T ^ ', 'T ^% ', 'T ^ & ', burada T = ' your_type '

Windows Çalışma Zamanı veya yönetilen türdeki bir operatör, türü işleç dönüş değerinin türüyle aynı olan en az bir parametreye sahip değildi.

Aşağıdaki örnek C2395 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C2395.cpp
// compile with: /clr /c
value struct V {
   static V operator *(int i, char c);   // C2395

   // OK
   static V operator *(V v, char c);
   // or
   static V operator *(int i, V& rv);
};
```
