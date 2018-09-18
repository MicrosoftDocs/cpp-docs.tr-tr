---
title: Derleyici Hatası C2384 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2384
dev_langs:
- C++
helpviewer_keywords:
- C2384
ms.assetid: 8145f7ad-31b1-406d-ac43-0d557feab635
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f3aa9ec8a6a94f53123c443a1149df7cdbc95c83
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46020465"
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