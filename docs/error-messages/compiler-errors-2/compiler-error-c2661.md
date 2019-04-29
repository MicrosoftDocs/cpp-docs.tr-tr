---
title: Derleyici Hatası C2661
ms.date: 11/04/2016
f1_keywords:
- C2661
helpviewer_keywords:
- C2661
ms.assetid: 60021467-71cd-451b-9877-23840c69309f
ms.openlocfilehash: 14052fa3676396fe2ffc6ca86196025e7adab7d6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360356"
---
# <a name="compiler-error-c2661"></a>Derleyici Hatası C2661

'function': hiçbir aşırı yüklenmiş işlev numarası parametre alır

Olası nedenler:

1. İşlev çağrısında yanlış gerçek parametre.

1. Eksik işlev bildirimi.

Aşağıdaki örnek, C2661 oluşturur:

```
// C2661.cpp
void func( int ){}
void func( int, int ){}
int main() {
   func( );   // C2661 func( void ) was not declared
   func( 1 );   // OK func( int ) was declared
}
```