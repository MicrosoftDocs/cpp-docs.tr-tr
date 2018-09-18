---
title: Derleyici Hatası C2179 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2179
dev_langs:
- C++
helpviewer_keywords:
- C2179
ms.assetid: f929bfc6-3964-4e54-87d6-7529b9b6c0b9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1b56437dfe5b9be75ae93dea46890d408ea2dc66
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46111640"
---
# <a name="compiler-error-c2179"></a>Derleyici Hatası C2179

'type': öznitelik bağımsız değişkeni tür parametreleri kullanamaz

Genel tür parametresi, çalışma zamanında çözülür. Ancak, bir öznitelik parametresi, derleme zamanında çözümlenmelidir. Bu nedenle, bir öznitelik bağımsız değişkeni olarak bir genel tür parametresi kullanılamaz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2179 oluşturur.

```
// C2179.cpp
// compile with: /clr
using namespace System;

public ref struct Attr : Attribute {
   Attr(Type ^ a) {
      x = a;
   }

   Type ^ x;
};

ref struct G {};

generic<typename T>
public ref class Z {
public:
   Type ^ d;
   [Attr(T::typeid)]   // C2179
   // try the following line instead
   // [Attr(G::typeid)]
   T t;
};
```