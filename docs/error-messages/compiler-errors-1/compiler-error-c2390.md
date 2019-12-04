---
title: Derleyici hatası C2390
ms.date: 11/04/2016
f1_keywords:
- C2390
helpviewer_keywords:
- C2390
ms.assetid: 06b749ee-d072-4db1-b229-715f2c0728b5
ms.openlocfilehash: 515e2e151d27dd2eb84fc1dc71b9197b36b14cbb
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745050"
---
# <a name="compiler-error-c2390"></a>Derleyici hatası C2390

' tanımlayıcı ': Hatalı depolama sınıfı ' belirleyicisi '

Depolama sınıfı genel kapsam tanımlayıcısı için geçerli değil. Varsayılan depolama sınıfı, geçersiz sınıf yerine kullanılır.

Olası çözümler:

- Tanımlayıcı bir işlevise, `extern` depolama ile bildirin.

- Tanımlayıcı bir biçimsel parametre veya yerel değişken ise, otomatik depolama ile bildirin.

- Tanımlayıcı genel bir değişkense, depolama sınıfı (otomatik depolama) olmadan bunu bildirin.

## <a name="example"></a>Örnek

- Aşağıdaki örnek C2390 oluşturur:

```cpp
// C2390.cpp
register int i;   // C2390

int main() {
   register int j;   // OK
}
```
