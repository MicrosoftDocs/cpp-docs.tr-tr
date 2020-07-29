---
title: Derleyici hatası C2390
ms.date: 11/04/2016
f1_keywords:
- C2390
helpviewer_keywords:
- C2390
ms.assetid: 06b749ee-d072-4db1-b229-715f2c0728b5
ms.openlocfilehash: 48012c0fe31b2017cad29cc98992c9b1121efa7c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221191"
---
# <a name="compiler-error-c2390"></a>Derleyici hatası C2390

' tanımlayıcı ': Hatalı depolama sınıfı ' belirleyicisi '

Depolama sınıfı genel kapsam tanımlayıcısı için geçerli değil. Varsayılan depolama sınıfı, geçersiz sınıf yerine kullanılır.

Olası çözümler:

- Tanımlayıcı bir işlev ise, depolama ile bildirin **`extern`** .

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
