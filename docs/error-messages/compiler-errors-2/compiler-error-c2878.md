---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2878'
title: Derleyici hatası C2878
ms.date: 11/04/2016
f1_keywords:
- C2878
helpviewer_keywords:
- C2878
ms.assetid: 83ee3de1-f554-49e8-a840-1f550cee7f69
ms.openlocfilehash: df79869572117eed851c5edd63f94234555cb990
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320479"
---
# <a name="compiler-error-c2878"></a>Derleyici hatası C2878

' name ': Bu ada sahip bir ad alanı veya sınıf yok

Tanımlı olmayan bir ad alanına veya sınıfa başvuru yaptınız.

Aşağıdaki örnek C2878 oluşturur:

```cpp
// C2878.cpp
// compile with: /c
namespace A {}
namespace B = C;   // C2878 namespace C doesn't exist
namespace B = A;
```
