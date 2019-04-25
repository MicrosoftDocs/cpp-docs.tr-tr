---
title: Derleyici Uyarısı (düzey 1) C4286
ms.date: 11/04/2016
f1_keywords:
- C4286
helpviewer_keywords:
- C4286
ms.assetid: 93eadd6c-6f36-413b-ba91-c9aa2314685a
ms.openlocfilehash: be02d330678eaab7f538ed092641f957bdcb01b2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62207075"
---
# <a name="compiler-warning-level-1-c4286"></a>Derleyici Uyarısı (düzey 1) C4286

'type1': satır numarası üzerinde taban sınıf ('type2') tarafından yakalandı

Belirtilen özel durum türü, bir önceki işleyici tarafından işlenir. İkinci yakalama türü ilk türünden türetilir. Özel durumlar bir temel sınıf için türetilmiş bir sınıf için özel durumlar yakalayın.

## <a name="example"></a>Örnek

```
//C4286.cpp
// compile with: /W1
#include <eh.h>
class C {};
class D : public  C {};
int main()
{
    try
    {
        throw "ooops!";
    }
    catch( C ) {}
    catch( D ) {}  // warning C4286, D is derived from C
}
```