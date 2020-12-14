---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3420'
title: Derleyici hatası C3420
ms.date: 11/04/2016
f1_keywords:
- C3420
helpviewer_keywords:
- C3420
ms.assetid: 99b53c77-f36b-4574-9199-b53111becccb
ms.openlocfilehash: 3c79693823255ed7335e5805c0ac17de5ddcead7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316017"
---
# <a name="compiler-error-c3420"></a>Derleyici hatası C3420

' Sonlandırıcı ': bir Sonlandırıcı sanal olamaz

Sonlandırıcı yalnızca kapsayan türünden bağımsız olmayan şekilde çağrılabilir. Bu nedenle, sanal sonlandırıcıyı bildirmek bir hatadır.

Daha fazla bilgi için bkz. [nasıl yapılır: sınıfları ve yapıları tanımlama ve kullanma (C++/CLI) içinde yok ediciler ve sonlandırıcılar](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3420 oluşturur.

```cpp
// C3420.cpp
// compile with: /clr /c
ref class R {
   virtual !R() {}   // C3420
};
```
