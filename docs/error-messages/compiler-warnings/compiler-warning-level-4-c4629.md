---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4629'
title: Derleyici Uyarısı (düzey 4) C4629
ms.date: 11/04/2016
f1_keywords:
- C4629
helpviewer_keywords:
- C4629
ms.assetid: 158cde12-bae5-4d43-b575-b52b35aaa0b9
ms.openlocfilehash: b357b72ca95682c33d3f4019d4663593c5c5ee8d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134179"
---
# <a name="compiler-warning-level-4-c4629"></a>Derleyici Uyarısı (düzey 4) C4629

digraf kullanıldı, ' diI ' karakter dizisi ' Char ' belirteci olarak yorumlanır (hedeflediğiniz bu değilse iki karakter arasına bir boşluk ekleyin)

[/Za](../../build/reference/za-ze-disable-language-extensions.md)'nin altında, derleyici bir dimi algıladığında uyarır.

Aşağıdaki örnek C4629 oluşturur:

```cpp
// C4629.cpp
// compile with: /Za /W4
int main()
<%   // C4629 <% digraph for {
}
```
