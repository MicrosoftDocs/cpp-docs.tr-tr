---
title: Derleyici Uyarısı (düzey 1) C4087
ms.date: 11/04/2016
f1_keywords:
- C4087
helpviewer_keywords:
- C4087
ms.assetid: 546e4d57-5c8e-422c-8ef1-92657336dad5
ms.openlocfilehash: fe2b4fadfb87726e81178a3530299dbb8620aec9
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626838"
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