---
title: Derleyici Hatası C3485 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3485
dev_langs:
- C++
helpviewer_keywords:
- C3485
ms.assetid: d67536f9-67a1-4ad9-9a94-d8bbbca3d0dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: db3eee53f23aa2cdc958b63faed11ead302f4b1e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46060752"
---
# <a name="compiler-error-c3485"></a>Derleyici Hatası C3485

bir lambda tanımında cv niteleyicileri bulunamaz

Kullanamazsınız bir `const` veya `volatile` bir lambda ifadesinin tanımının bir parçası olarak niteleyicisi.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Kaldırma `const` veya `volatile` , lambda ifadesinin tanımından niteleyicisi.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3485 oluşturur, bunu kullandığından `const` niteleyicisi bir lambda ifadesinin tanımının bir parçası olarak:

```
// C3485.cpp

int main()
{
   auto x = []() const mutable {}; // C3485
}
```

## <a name="see-also"></a>Ayrıca Bkz.

[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)