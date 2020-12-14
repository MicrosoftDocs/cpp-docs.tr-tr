---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3195'
title: Derleyici hatası C3195
ms.date: 11/04/2016
f1_keywords:
- C3195
helpviewer_keywords:
- C3195
ms.assetid: 97e4f681-812b-49e8-ba57-24b7817e3cd8
ms.openlocfilehash: 691aa50fcb091f240253363a23671ac4db70894f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203802"
---
# <a name="compiler-error-c3195"></a>Derleyici hatası C3195

' operator ': ayrılmıştır ve bir başvuru sınıfının veya değer türünün üyesi olarak kullanılamaz. CLR veya WinRT işleçleri ' operator ' anahtar sözcüğü kullanılarak tanımlanmalıdır

Derleyici C++ için Yönetilen Uzantılar sözdizimini kullanarak bir operatör tanımı algıladı. İşleçler için C++ sözdizimini kullanmanız gerekir.

Aşağıdaki örnek C3195 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C3195.cpp
// compile with: /clr /LD
#using <mscorlib.dll>
value struct V {
   static V op_Addition(V v, int i);   // C3195
   static V operator +(V v, char c);   // OK for new C++ syntax
};
```
