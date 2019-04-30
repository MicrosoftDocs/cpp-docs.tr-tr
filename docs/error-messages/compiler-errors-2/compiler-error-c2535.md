---
title: Derleyici Hatası C2535
ms.date: 11/04/2016
f1_keywords:
- C2535
helpviewer_keywords:
- C2535
ms.assetid: a958f83e-e2bf-4a59-b44b-d406ec325d7e
ms.openlocfilehash: b2b5452cfe59284d56b019674ffbabbda0dc62d1
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344713"
---
# <a name="compiler-error-c2535"></a>Derleyici Hatası C2535

'identifier': üye işlev önceden tanımlandı veya bildirildi

Birden fazla tanım veya aşırı yüklenmiş bir işlevin bildirimi aynı biçimsel parametre listesinde kullanarak bu hataya neden.

Dispose işlev nedeniyle C2535 alırsanız, bkz. [yok ediciler ve sonlandırıcılar](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers) daha fazla bilgi için.

Aşağıdaki örnek, C2535 oluşturur:

```
// C2535.cpp
// compile with: /c
class C {
public:
   void func();   // forward declaration
   void func() {}   // C2535
};
```