---
title: Derleyici Hatası C2333 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2333
dev_langs:
- C++
helpviewer_keywords:
- C2333
ms.assetid: 2636fc1e-d3e7-4e68-8628-3c81a99ba813
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 850ad69a84100106c7a29608aaf85ecf5d592cde
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46114130"
---
# <a name="compiler-error-c2333"></a>Derleyici Hatası C2333

'function': işlev bildiriminde; hata işlev gövdesi atlanıyor

Üye işlevleri kendi sınıf içinde tanımlandığına için başka bir hatadan sonra bu hata oluşur.

Aşağıdaki örnek, C2333 oluşturur:

```
// C2333.cpp
struct s1 {
   s1(s1) {}   // C2333
};
```