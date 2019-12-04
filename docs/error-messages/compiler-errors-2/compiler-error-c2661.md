---
title: Derleyici hatası C2661
ms.date: 11/04/2016
f1_keywords:
- C2661
helpviewer_keywords:
- C2661
ms.assetid: 60021467-71cd-451b-9877-23840c69309f
ms.openlocfilehash: e4d0e8a1c707374e0e93a5687351a9360fa17c0f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756051"
---
# <a name="compiler-error-c2661"></a>Derleyici hatası C2661

' function ': aşırı yüklenmiş hiçbir işlev sayı parametresi alır

Olası nedenler:

1. İşlev çağrısında yanlış gerçek parametreler.

1. İşlev bildirimi eksik.

Aşağıdaki örnek C2661 oluşturur:

```cpp
// C2661.cpp
void func( int ){}
void func( int, int ){}
int main() {
   func( );   // C2661 func( void ) was not declared
   func( 1 );   // OK func( int ) was declared
}
```
