---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2535'
title: Derleyici hatası C2535
ms.date: 11/04/2016
f1_keywords:
- C2535
helpviewer_keywords:
- C2535
ms.assetid: a958f83e-e2bf-4a59-b44b-d406ec325d7e
ms.openlocfilehash: 149ddabcde7364513379701c55d4801fd403206b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258089"
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
