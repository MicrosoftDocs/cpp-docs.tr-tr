---
title: Derleyici hatası C2878
ms.date: 11/04/2016
f1_keywords:
- C2878
helpviewer_keywords:
- C2878
ms.assetid: 83ee3de1-f554-49e8-a840-1f550cee7f69
ms.openlocfilehash: faf50edfcddc64a75062672175ab7fbad63081c1
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74736319"
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
