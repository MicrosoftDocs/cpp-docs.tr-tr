---
title: Derleyici Uyarısı (düzey 1) C4178
ms.date: 11/04/2016
f1_keywords:
- C4178
helpviewer_keywords:
- C4178
ms.assetid: 2c2c8f97-a5c4-47cd-8dd2-beea172613f3
ms.openlocfilehash: 76e2b0e6ee42e8f32eb462336721d860cff006a5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391679"
---
# <a name="compiler-warning-level-1-c4178"></a>Derleyici Uyarısı (düzey 1) C4178

Case sabiti 'sabiti' türü için çok büyük switch ifadesi

Bir servis talebi sabiti bir `switch` ifade türünde olduğu, atandığı uymuyor.

## <a name="example"></a>Örnek

```
// C4178.cpp
// compile with: /W1
int main()
{
    int i;  // maximum size of unsigned long int is 4294967295
    switch( i )
    {
        case 4294967295:   // OK
            break;
        case 4294967296:   // C4178
            break;
    }
}
```