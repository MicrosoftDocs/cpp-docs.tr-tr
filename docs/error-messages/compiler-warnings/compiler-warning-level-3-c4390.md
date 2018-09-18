---
title: Derleyici Uyarısı (Düzey 3) C4390 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4390
dev_langs:
- C++
helpviewer_keywords:
- C4390
ms.assetid: c95c2f1b-9bce-4b1f-a80c-565d4cde0b1e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 83131119e360bcf8193c2d6c8ca5a3cd09341516
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054200"
---
# <a name="compiler-warning-level-3-c4390"></a>Derleyici Uyarısı (Düzey 3) C4390

';': boş denetlenen deyim bulundu; Bu amaç mi?

Noktalı virgül, hiçbir yönergeleri içeren bir denetim deyimidir sonra bulunamadı.

Makro nedeniyle C4390 alırsanız, kullanmanız gereken [uyarı](../../preprocessor/warning.md) pragma makro içeren modülünde C4390 devre dışı bırakmak için.

Aşağıdaki örnek, C4390 oluşturur:

```
// C4390.cpp
// compile with: /W3
int main() {
   int i = 0;
   if (i);   // C4390
      i++;
}
```