---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3836'
title: Derleyici hatası C3836
ms.date: 11/04/2016
f1_keywords:
- C3836
helpviewer_keywords:
- C3836
ms.assetid: 254f851b-7b7d-4c34-a740-fcf72f6a636a
ms.openlocfilehash: c7e05bbf95facf5b8552b4442138cc38b86703c0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180883"
---
# <a name="compiler-error-c3836"></a>Derleyici hatası C3836

statik oluşturucunun üye Başlatıcı listesi olmasına izin verilmiyor

Yönetilen bir sınıf, üye başlatma listesi olan bir statik oluşturucuya sahip olamaz. Statik Sınıf oluşturucuları, sınıf başlatma işlemi için ortak dil çalışma zamanı tarafından çağrılır ve statik veri üyeleri başlatılıyor.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3836 oluşturur:

```cpp
// C3836a.cpp
// compile with: /clr
ref class M
{
   static int s_i;

public:
   static M() :  s_i(1234)   // C3836, delete initializer to resolve
   {
   }
};

int main()
{
}
```
