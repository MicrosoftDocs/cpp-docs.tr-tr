---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2661'
title: Derleyici hatası C2661
ms.date: 11/04/2016
f1_keywords:
- C2661
helpviewer_keywords:
- C2661
ms.assetid: 60021467-71cd-451b-9877-23840c69309f
ms.openlocfilehash: 524d270fd15b529bad13a5ff1e5e46f3d5d9dd04
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170028"
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
