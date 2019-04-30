---
title: Derleyici Hatası C2531
ms.date: 11/04/2016
f1_keywords:
- C2531
helpviewer_keywords:
- C2531
ms.assetid: c49afe15-55f8-4dc8-ac01-bf653622a7db
ms.openlocfilehash: 03e055e9830b8168fb19885a04c8d40d24713d23
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378979"
---
# <a name="compiler-error-c2531"></a>Derleyici Hatası C2531

'identifier': bir bit alanı geçersiz başvuru

Bit alanları başvuruları izin verilmez.

Aşağıdaki örnek, C2531 oluşturur:

```
// C2531.cpp
// compile with: /c
class P {
   int &b1 : 10;   // C2531
   int b2 : 10;   // OK
};
```