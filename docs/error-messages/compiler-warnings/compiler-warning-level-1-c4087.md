---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4087'
title: Derleyici Uyarısı (düzey 1) C4087
ms.date: 11/04/2016
f1_keywords:
- C4087
helpviewer_keywords:
- C4087
ms.assetid: 546e4d57-5c8e-422c-8ef1-92657336dad5
ms.openlocfilehash: 2375ad5c99862f7ee8a0156ca1b3d637b95f0569
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267553"
---
# <a name="compiler-warning-level-1-c4087"></a>Derleyici Uyarısı (düzey 1) C4087

' function ': ' void ' parametre listesiyle bildiriliyor

İşlev bildiriminde hiç biçimsel parametre yoktur, ancak işlev çağrısının gerçek parametreleri vardır. Ek parametreler, işlevin çağırma kuralına göre geçirilir.

Bu uyarı C derleyicisi içindir.

## <a name="example"></a>Örnek

```c
// C4087.c
// compile with: /W1
int f1( void ) {
}

int main() {
   f1( 10 );   // C4087
}
```
