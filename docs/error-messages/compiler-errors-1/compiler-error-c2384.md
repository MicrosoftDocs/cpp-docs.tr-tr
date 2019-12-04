---
title: Derleyici hatası C2384
ms.date: 11/04/2016
f1_keywords:
- C2384
helpviewer_keywords:
- C2384
ms.assetid: 8145f7ad-31b1-406d-ac43-0d557feab635
ms.openlocfilehash: 2ce5c2f2540fbd2aca3509fa1dac55073a002abb
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745271"
---
# <a name="compiler-error-c2384"></a>Derleyici hatası C2384

' Member ': yönetilen veya WinRT sınıfının üyesine __declspec (thread) uygulanamıyor

[İş parçacığı](../../cpp/thread.md) `__declspec` değiştiricisi yönetilen veya Windows çalışma zamanı sınıfının bir üyesi üzerinde kullanılamaz.

Yönetilen koddaki statik iş parçacığı yerel depolaması, yalnızca statik olarak yüklenen dll 'Ler için kullanılabilir — işlem başladığında DLL 'nin statik olarak yüklenmesi gerekir. Windows Çalışma Zamanı, iş parçacığı yerel depolamayı desteklemez.

Aşağıdaki satır C2384 oluşturur ve C++/CLI kodunda nasıl düzeltileceğini gösterir:

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
