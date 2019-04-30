---
title: Derleyici Hatası C2390
ms.date: 11/04/2016
f1_keywords:
- C2390
helpviewer_keywords:
- C2390
ms.assetid: 06b749ee-d072-4db1-b229-715f2c0728b5
ms.openlocfilehash: 89f6ebb02326413e8dca67d333e555321da4e645
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393642"
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