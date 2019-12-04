---
title: Derleyici hatası C2870
ms.date: 11/04/2016
f1_keywords:
- C2870
helpviewer_keywords:
- C2870
ms.assetid: 80523ee9-1fd3-4dc4-8a77-5083deb99066
ms.openlocfilehash: 3b006592723df1222d05e39b3bc9e5729efc8aa6
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755037"
---
# <a name="compiler-error-c2870"></a>Derleyici hatası C2870

' name ': ad alanı tanımı dosya kapsamında ya da başka bir ad alanı tanımının hemen içinde yer almalıdır

Ad alanı `name` yanlış tanımladınız. Ad alanları, dosya kapsamında (tüm bloklar ve sınıflar dışında) veya başka bir ad alanının hemen içinde tanımlanmalıdır.

Aşağıdaki örnek C2870 oluşturur:

```cpp
// C2870.cpp
// compile with: /c
int main() {
   namespace A { int i; };   // C2870
}
```
