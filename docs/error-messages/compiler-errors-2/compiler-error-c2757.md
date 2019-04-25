---
title: Derleyici Hatası C2757
ms.date: 11/04/2016
f1_keywords:
- C2757
helpviewer_keywords:
- C2757
ms.assetid: 421f102f-8a32-4d47-a109-811ddf2c909d
ms.openlocfilehash: 98b43a2f3c0888fc385226cd80889b9911c84690
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62227922"
---
# <a name="compiler-error-c2757"></a>Derleyici Hatası C2757

'symbol': Bu ada sahip bir simge zaten var ve bu nedenle bu adı bir ad alanı adı olarak kullanılamaz

Başvurulan bir derlemede bir ad alanı tanımlayıcısı zaten kullanıldığından geçerli derlemede kullanılan bir simge.

Aşağıdaki örnek, C2757 oluşturur:

```
// C2757a.cpp
// compile with: /clr /LD
public ref class Nes {};
```

Ardından,

```
// C2757b.cpp
// compile with: /clr /c
#using <C2757a.dll>

namespace Nes {    // C2757
// try the following line instead
// namespace Nes2 {
   public ref class X {};
}
```
