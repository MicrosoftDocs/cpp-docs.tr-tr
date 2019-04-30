---
title: Derleyici Hatası C3273
ms.date: 11/04/2016
f1_keywords:
- C3273
helpviewer_keywords:
- C3273
ms.assetid: 1d2ce9d9-222b-4cab-94e2-d2c1a9f5ebe0
ms.openlocfilehash: 466a9d6687dd5bfdab80ce1dfc9096ef7540ebaa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62382339"
---
# <a name="compiler-error-c3273"></a>Derleyici Hatası C3273

__finally yönetilmeyen kodu bir özel durum bloğunda kullanılamaz.

Aşağıdaki örnek, C3273 oluşturur:

```
// C3273.cpp
// compile with: /GX
int main()
{
   try
   {
   }
   catch (int)
   {
   }
   __finally   // C3273, remove __finally clause
   {
   }
}
```