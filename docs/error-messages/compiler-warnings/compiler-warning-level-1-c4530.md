---
title: Derleyici Uyarısı (düzey 1) C4530
ms.date: 11/04/2016
f1_keywords:
- C4530
helpviewer_keywords:
- C4530
ms.assetid: a04dcdb2-84db-459d-9e5e-4e743887465f
ms.openlocfilehash: 69ca60e2cba338bf1bd1ac3470e583739e72a68e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186458"
---
# <a name="compiler-warning-level-1-c4530"></a>Derleyici Uyarısı (düzey 1) C4530

C++özel durum işleyicisi kullanıldı, ancak geriye doğru izleme semantiği etkin değil. /EHsc belirtin

C++özel durum işleme kullanıldı ancak [/EHsc](../../build/reference/eh-exception-handling-model.md) seçilmedi.

/EHsc seçeneği etkinleştirilmediğinde, oluşturma işlemi yapan işlev ve throw 'u yakalayan işlev arasında çerçevede otomatik depolamaya sahip bir nesne yok edilmez. Ancak, bir **TRY** veya **catch** bloğunda oluşturulan otomatik depolamaya sahip bir nesne yok edilir.

Aşağıdaki örnek C4530 oluşturur:

```cpp
// C4530.cpp
// compile with: /W1
int main() {
   try{} catch(int*) {}   // C4530
}
```

Uyarıyı çözümlemek için, örneği/EHsc ile derleyin.
