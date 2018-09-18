---
title: Derleyici Uyarısı (düzey 1) C4530 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4530
dev_langs:
- C++
helpviewer_keywords:
- C4530
ms.assetid: a04dcdb2-84db-459d-9e5e-4e743887465f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bbfbc67377dd48eeb692bdd4cac1f113fbdf7f6a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110464"
---
# <a name="compiler-warning-level-1-c4530"></a>Derleyici Uyarısı (düzey 1) C4530

C++ özel durum işleyicisi kullanılır, ancak geriye doğru izleme semantiği etkinleştirilmedi. / Ehsc belirtin

C++ özel durum işleme kullanıldı ancak [/ehsc](../../build/reference/eh-exception-handling-model.md) seçilmedi.

/ Ehsc seçeneği etkinleştirilmemiş olduğunda otomatik depolama çerçevesinde, throw yapılması ve throw yakalama işlevleri arasında olan bir nesne yok edilmez. Ancak, otomatik depolamalı bir nesnenin oluşturulup bir **deneyin** veya **catch** blok silinecektir.

Aşağıdaki örnek, C4530 oluşturur:

```
// C4530.cpp
// compile with: /W1
int main() {
   try{} catch(int*) {}   // C4530
}
```

Örnek uyarı çözümlemek için/ehsc ile derleyin.