---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2390'
title: Derleyici hatası C2390
ms.date: 11/04/2016
f1_keywords:
- C2390
helpviewer_keywords:
- C2390
ms.assetid: 06b749ee-d072-4db1-b229-715f2c0728b5
ms.openlocfilehash: 91539cea6ed89c02734c08f068f3d6474283dfa9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337591"
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
