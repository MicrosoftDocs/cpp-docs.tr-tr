---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2482'
title: Derleyici hatası C2482
ms.date: 09/15/2017
f1_keywords:
- C2482
helpviewer_keywords:
- C2482
ms.assetid: 98c87da2-625c-4cc2-9bf7-78d15921e779
ms.openlocfilehash: 1ffde4d7ea9f4eccdd643b3ac6efe0545775816a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123935"
---
# <a name="compiler-error-c2482"></a>Derleyici hatası C2482

>'*tanımlayıcı*': yönetilen/WinRT kodunda ' Thread ' verilerinin dinamik olarak başlatılmasına izin verilmiyor

## <a name="remarks"></a>Açıklamalar

Yönetilen veya WinRT kodunda, [__declspec (thread)](../../cpp/thread.md) depolama sınıfı değiştirici özniteliği veya [thread_local](../../cpp/storage-classes-cpp.md#thread_local) depolama sınıfı Belirleyicisi kullanılarak belirtilen değişkenler, çalışma zamanında değerlendirme gerektiren bir ifadeyle başlatılamaz. `__declspec(thread)`Bu çalışma zamanı ortamlarında bir statik ifade başlatmak veya veri eklemek için gerekir **`thread_local`** .

## <a name="example"></a>Örnek

Aşağıdaki örnek, yönetilen (**/clr**) ve WinRT (**/ZW**) kodunda C2482 oluşturur:

```cpp
// C2482.cpp
// For managed example, compile with: cl /EHsc /c /clr C2482.cpp
// For WinRT example, compile with: cl /EHsc /c /ZW C2482.cpp
#define Thread __declspec( thread )
Thread int tls_i1 = tls_i1;   // C2482

int j = j;   // OK in C++; C error
Thread int tls_i2 = sizeof( tls_i2 );   // Okay in C and C++
```

Bu sorunu onarmak için, sabit, veya statik bir ifade kullanarak iş parçacığı yerel depolamayı başlatın **`constexpr`** . Her iş parçacığına özgü başlatmayı ayrı olarak gerçekleştirin.
