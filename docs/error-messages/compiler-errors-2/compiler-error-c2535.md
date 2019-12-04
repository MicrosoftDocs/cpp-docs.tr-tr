---
title: Derleyici hatası C2535
ms.date: 11/04/2016
f1_keywords:
- C2535
helpviewer_keywords:
- C2535
ms.assetid: a958f83e-e2bf-4a59-b44b-d406ec325d7e
ms.openlocfilehash: f5cecd847837214f6392bead624e5377cef4833f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758651"
---
# <a name="compiler-error-c2535"></a>Derleyici hatası C2535

' tanımlayıcı ': üye işlev önceden tanımlandı veya bildiriliyor

Bu hata, aşırı yüklenmiş bir işlevin birden fazla tanımında veya bildiriminde aynı biçimsel parametre listesinin kullanılmasıyla kaynaklanabilir.

Dispose işlevi nedeniyle C2535 alırsanız daha fazla bilgi için yok [ediciler ve sonlandırıcılar](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers) bölümüne bakın.

Aşağıdaki örnek C2535 oluşturur:

```cpp
// C2535.cpp
// compile with: /c
class C {
public:
   void func();   // forward declaration
   void func() {}   // C2535
};
```
