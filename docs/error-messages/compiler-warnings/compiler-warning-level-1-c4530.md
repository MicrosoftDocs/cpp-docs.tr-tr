---
title: Derleyici Uyarısı (düzey 1) C4530
ms.date: 11/04/2016
f1_keywords:
- C4530
helpviewer_keywords:
- C4530
ms.assetid: a04dcdb2-84db-459d-9e5e-4e743887465f
ms.openlocfilehash: a542f9b6bb73e561592e1e779aa6ee493612e6ac
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160724"
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