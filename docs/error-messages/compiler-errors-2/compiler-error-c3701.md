---
title: Derleyici Hatası C3701
ms.date: 11/04/2016
f1_keywords:
- C3701
helpviewer_keywords:
- C3701
ms.assetid: a7faaa87-d2f5-4d6a-9a2f-5cab2d24a648
ms.openlocfilehash: 2efbf3c48b7c366d262facac9cebb4f72d9f1513
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344553"
---
# <a name="compiler-error-c3701"></a>Derleyici Hatası C3701

'function': event_source sahip olay yok

Kullanmaya çalıştığınız [event_source](../../windows/event-source.md) hiçbir olay yöntemleri içeren bir sınıf. Bu hatayı düzeltmek için bir veya daha fazla olayı sınıfına ekleyin.

Aşağıdaki örnek, C3701 oluşturur:

```
// C3701.cpp
[ event_source(native) ]
class CEventSrc {
public:
   // uncomment the following line to resolve this C3701
   // __event void fireEvent(int i);
};   // C3701

int main() {
}
```