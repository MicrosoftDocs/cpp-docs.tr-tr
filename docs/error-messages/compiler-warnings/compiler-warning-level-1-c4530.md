---
title: Derleyici Uyarısı (düzey 1) C4530
ms.date: 11/04/2016
f1_keywords:
- C4530
helpviewer_keywords:
- C4530
ms.assetid: a04dcdb2-84db-459d-9e5e-4e743887465f
ms.openlocfilehash: 3139d321bca64b9938badebdabccd3ca1eb96d11
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966257"
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