---
title: Derleyici Hatası C3420
ms.date: 11/04/2016
f1_keywords:
- C3420
helpviewer_keywords:
- C3420
ms.assetid: 99b53c77-f36b-4574-9199-b53111becccb
ms.openlocfilehash: 3db109598ce0741ca34a230d8925994543bcb5ea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182463"
---
# <a name="compiler-error-c3420"></a>Derleyici Hatası C3420

'Sonlandırıcı': bir sonlandırıcı sanal olamaz

Bir sonlandırıcı yalnızca sanal olmayan kapsayan türdeki çağrılabilir. Bu nedenle, bunu sanal bir sonlandırıcı bildirmek için bir hatadır.

Daha fazla bilgi için [yok ediciler ve sonlandırıcılar, nasıl yapılır: Sınıfları ve yapıları tanımlama ve kullanma (C++/CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3420 oluşturur.

```
// C3420.cpp
// compile with: /clr /c
ref class R {
   virtual !R() {}   // C3420
};
```