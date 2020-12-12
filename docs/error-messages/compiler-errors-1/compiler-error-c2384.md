---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2384'
title: Derleyici hatası C2384
ms.date: 11/04/2016
f1_keywords:
- C2384
helpviewer_keywords:
- C2384
ms.assetid: 8145f7ad-31b1-406d-ac43-0d557feab635
ms.openlocfilehash: f72db8d5beb871bbb9adf1cdc234769705db2b9d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272519"
---
# <a name="compiler-error-c2384"></a>Derleyici hatası C2384

' Member ': yönetilen veya WinRT sınıfının üyesine __declspec (thread) uygulanamıyor

[İş parçacığı](../../cpp/thread.md) **`__declspec`** değiştiricisi yönetilen veya Windows çalışma zamanı sınıfının bir üyesi üzerinde kullanılamaz.

Yönetilen koddaki statik iş parçacığı yerel depolaması, yalnızca statik olarak yüklenen dll 'Ler için kullanılabilir — işlem başladığında DLL 'nin statik olarak yüklenmesi gerekir. Windows Çalışma Zamanı, iş parçacığı yerel depolamayı desteklemez.

Aşağıdaki satır C2384 oluşturur ve C++/CLı kodunda nasıl düzeltileceğini gösterir:

```cpp
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
