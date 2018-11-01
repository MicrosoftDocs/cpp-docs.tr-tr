---
title: Derleyici Hatası C2951
ms.date: 11/04/2016
f1_keywords:
- C2951
helpviewer_keywords:
- C2951
ms.assetid: c6f95aa2-c894-425b-a51c-d40d70c8daa1
ms.openlocfilehash: dbc7186edfce6cc12a38fb2fc1dda08ac4a181c7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50638704"
---
# <a name="compiler-error-c2951"></a>Derleyici Hatası C2951

tür bildirimleri yalnızca genel ad alanında izin verilen veya sınıf kapsamında

Bir genel veya genel dışında Şablon sınıfı veya ad alanı kapsamında bildiremezsiniz. Genel veya şablon bildirimlerinizde bir içerme dosyasında değişiklik yaparsanız, genel kapsamda içerme dosyası olduğundan emin olun.

Aşağıdaki örnek, C2951 oluşturur:

```
// C2951.cpp
template <class T>
class A {};

int main() {
   template <class T>   // C2951
   class B {};
}
```

C2951, genel türler kullanırken da meydana gelebilir:

```
// C2951b.cpp
// compile with: /clr /c

// OK
generic <class T>
ref class GC { };

int main() {
   generic <class T> ref class GC2 {};   // C2951
}
```