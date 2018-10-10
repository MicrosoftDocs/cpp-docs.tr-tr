---
title: Derleyici Hatası C2535 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2535
dev_langs:
- C++
helpviewer_keywords:
- C2535
ms.assetid: a958f83e-e2bf-4a59-b44b-d406ec325d7e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5d9bb276ded32d8b263e64a8ea70f2c1953ee24b
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/09/2018
ms.locfileid: "48890302"
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