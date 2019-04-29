---
title: Derleyici Hatası C3195
ms.date: 11/04/2016
f1_keywords:
- C3195
helpviewer_keywords:
- C3195
ms.assetid: 97e4f681-812b-49e8-ba57-24b7817e3cd8
ms.openlocfilehash: 4a54a9c629a1abaa4f1c5d15d06448e82cf25561
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62329107"
---
# <a name="compiler-error-c3195"></a>Derleyici Hatası C3195

'operator': ayrılmış ve bir başvuru sınıfının veya değer türünün üyesi olarak kullanılamaz. CLR veya WinRT işleçleri 'operator' anahtar sözcüğü kullanılarak tanımlanmalıdır.

Derleyici C++ sözdizimi için Yönetilen Uzantılar'ı kullanarak bir işleç tanımını algıladı. İşleçler için C++ sözdizimini kullanmanız gerekir.

Aşağıdaki örnek, C3195 oluşturur ve bu sorunun nasıl gösterir:

```
// C3195.cpp
// compile with: /clr /LD
#using <mscorlib.dll>
value struct V {
   static V op_Addition(V v, int i);   // C3195
   static V operator +(V v, char c);   // OK for new C++ syntax
};
```