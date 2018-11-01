---
title: Derleyici Hatası C3846
ms.date: 11/04/2016
f1_keywords:
- C3846
helpviewer_keywords:
- C3846
ms.assetid: c470f8a5-106b-4efb-b8dc-e1319e04130f
ms.openlocfilehash: 788f03e4364404ad5c30b7edcba8b743c7f201ad
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50651223"
---
# <a name="compiler-error-c3846"></a>Derleyici Hatası C3846

'symbol': 'assembly2' değerinden simge alınamıyor: 'symbol', 'assembly1' başka bir derleme zaten alınmış olarak

Başvurulan bir derleme, daha önce içeri aktarıldığından başvurulan bir derleme bir sembolü içeri aktarılamadı.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3846 oluşturur:

```
// C3846a.cpp
// compile with: /LD /clr
public ref struct G
{
};
```

Ve bunu derleyin:

```
// C3846b.cpp
// compile with: /clr
#using "c3846a.dll"
#using "c3846a.obj"   // C3846

int main()
{
}
```
