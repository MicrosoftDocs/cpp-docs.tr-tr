---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2870'
title: Derleyici hatası C2870
ms.date: 11/04/2016
f1_keywords:
- C2870
helpviewer_keywords:
- C2870
ms.assetid: 80523ee9-1fd3-4dc4-8a77-5083deb99066
ms.openlocfilehash: 74e7f2de5cfbb5aca6bd653f5711b989de4ef326
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333769"
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
