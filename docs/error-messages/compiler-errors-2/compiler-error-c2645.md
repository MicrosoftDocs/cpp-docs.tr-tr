---
title: Derleyici Hatası C2645
ms.date: 11/04/2016
f1_keywords:
- C2645
helpviewer_keywords:
- C2645
ms.assetid: 6609c2fa-c3b2-4a6b-8e8d-58fb52f67175
ms.openlocfilehash: 9df9f41da3d4cbef97511b979845c5a6b404614b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152598"
---
# <a name="compiler-error-c2645"></a>Derleyici Hatası C2645

üye işaretçisinin tam adı yok (bulundu ':: *')

Bir üye işaretçisi bildirimi bir sınıf belirtmiyor.

Aşağıdaki örnek, C2645 oluşturur:

```
// C2645.cpp
class A {};
int main() {
   int B::* bp;   // C2645 B not defined
   int A::* ap;   // OK
}
```