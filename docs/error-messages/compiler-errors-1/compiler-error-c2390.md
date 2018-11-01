---
title: Derleyici Hatası C2390
ms.date: 11/04/2016
f1_keywords:
- C2390
helpviewer_keywords:
- C2390
ms.assetid: 06b749ee-d072-4db1-b229-715f2c0728b5
ms.openlocfilehash: 89f6ebb02326413e8dca67d333e555321da4e645
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50595879"
---
# <a name="compiler-error-c2390"></a>Derleyici Hatası C2390

'identifier': Geçersiz depolama sınıfı 'belirticisi'

Depolama sınıfı genel kapsam tanımlayıcısı geçerli değil. Varsayılan depolama sınıfı geçersiz sınıf yerine kullanılır.

Olası çözümler:

- Bir işlev tanımlayıcı ise ile bildirimini `extern` depolama.

- Tanımlayıcı bir biçimsel parametre veya yerel değişken ise, otomatik depolama ile bildirin.

- Tanımlayıcı bir genel değişken ise, hiçbir depolama sınıfı (otomatik depolama) bildirin.

## <a name="example"></a>Örnek

- Aşağıdaki örnek, C2390 oluşturur:

```
// C2390.cpp
register int i;   // C2390

int main() {
   register int j;   // OK
}
```