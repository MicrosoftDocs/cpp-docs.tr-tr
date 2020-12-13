---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2395'
title: Derleyici hatası C2395
ms.date: 11/04/2016
f1_keywords:
- C2395
helpviewer_keywords:
- C2395
ms.assetid: 2d9e3b28-8c2c-4f41-a57f-61ef88fc2af0
ms.openlocfilehash: 86b6123646ca91945a861e9b9822076877421ac8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145476"
---
# <a name="compiler-error-c2395"></a>Derleyici hatası C2395

' your_type:: operator'op ' ': CLR veya WinRT işleci geçerli değil. En az bir parametre şu türlerde olmalıdır: 'T ', 'T% ', 'T& ', 'T ^ ', 'T ^% ', 'T ^& ', burada T = ' your_type '

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
