---
title: Derleyici Hatası C3420
ms.date: 11/04/2016
f1_keywords:
- C3420
helpviewer_keywords:
- C3420
ms.assetid: 99b53c77-f36b-4574-9199-b53111becccb
ms.openlocfilehash: 3db109598ce0741ca34a230d8925994543bcb5ea
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50645945"
---
# <a name="compiler-error-c3420"></a>Derleyici Hatası C3420

'Sonlandırıcı': bir sonlandırıcı sanal olamaz

Bir sonlandırıcı yalnızca sanal olmayan kapsayan türdeki çağrılabilir. Bu nedenle, bunu sanal bir sonlandırıcı bildirmek için bir hatadır.

Daha fazla bilgi için [yok ediciler ve sonlandırıcılar, nasıl yapılır: sınıfları ve yapıları tanımlama ve kullanma (C + +/ CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3420 oluşturur.

```
// C3420.cpp
// compile with: /clr /c
ref class R {
   virtual !R() {}   // C3420
};
```