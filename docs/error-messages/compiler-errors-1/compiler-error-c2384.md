---
title: Derleyici Hatası C2384
ms.date: 11/04/2016
f1_keywords:
- C2384
helpviewer_keywords:
- C2384
ms.assetid: 8145f7ad-31b1-406d-ac43-0d557feab635
ms.openlocfilehash: 1909fb999dd0f60224029b726f773c11fa69ee40
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50460326"
---
# <a name="compiler-error-c2384"></a>Derleyici Hatası C2384

'member': gt;__declspec(thread) için yönetilen bir üyesi veya WinRT sınıfı uygulanamıyor

[İş parçacığı](../../cpp/thread.md) `__declspec` yönetilen bir üyesi ya da Windows çalışma zamanı sınıf değiştiricisi kullanılamaz.

Statik iş parçacığı yerel depolama yönetilen kodda yalnızca kullanılabilir için statik olarak yüklenen DLL'lerin — işlem başladığında DLL statik olarak yüklenmesi gerekir. Windows çalışma zamanı iş parçacığı yerel depolama desteklemez.

Aşağıdaki satırı C2384 oluşturur ve C +'da nasıl düzeltileceğini gösteren +/ CLI kodu:

```
// C2384.cpp
// compile with: /clr /c
public ref class B {
public:
   __declspec( thread ) static int tls_i = 1;   // C2384

   // OK - declare with attribute instead
   [System::ThreadStaticAttribute]
   static int tls_j;
};
```