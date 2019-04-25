---
title: Derleyici Hatası C2433
ms.date: 11/04/2016
f1_keywords:
- C2433
helpviewer_keywords:
- C2433
ms.assetid: 7079fedd-6059-4125-82ef-ebe275f1f9d1
ms.openlocfilehash: 8a98fcf7570605694569b7ae466ae0a3c7cf14bb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166743"
---
# <a name="compiler-error-c2433"></a>Derleyici Hatası C2433

'identifier': veri bildirimlerinde izin verilmeyen'değiştiricisi '

`friend`, `virtual`, Ve `inline` değiştiricilerini veri bildirimleri için kullanılamaz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2433 oluşturur.

```
// C2433.cpp
class C{};

int main() {
   inline C c;   // C2433
}
```