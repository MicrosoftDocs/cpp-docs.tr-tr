---
title: Derleyici Uyarısı (düzey 4) C4125 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4125
dev_langs:
- C++
helpviewer_keywords:
- C4125
ms.assetid: a081d1f4-0789-4915-91df-7ff0b28ca245
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7042dd8689bf5a9bafc35d6bdaa6028f0c52df2a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46087246"
---
# <a name="compiler-warning-level-4-c4125"></a>Derleyici Uyarısı (düzey 4) C4125

ondalık basamak sekizlik kaçış sırasını sonlandırıyor

Derleyici, ondalık basamak olmadan sekizlik sayı değerlendirir ve ondalık basamak karakteri olduğunu varsayar.

## <a name="example"></a>Örnek

```
// C4125a.cpp
// compile with: /W4
char array1[] = "\709"; // C4125
int main()
{
}
```

9 basamaklı bir karakter olarak amaçlanıyorsa, örnek şu şekilde düzeltin:

```
// C4125b.cpp
// compile with: /W4
char array[] = "\0709";  // C4125 String containing "89"
int main()
{
}
```