---
title: Derleyici Hatası C3420 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3420
dev_langs:
- C++
helpviewer_keywords:
- C3420
ms.assetid: 99b53c77-f36b-4574-9199-b53111becccb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3997bc0744bf1e1db34fe7ce1de666ebd3e3b8cd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46078575"
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