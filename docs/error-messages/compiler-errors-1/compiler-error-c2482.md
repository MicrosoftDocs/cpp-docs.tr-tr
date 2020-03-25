---
title: Derleyici hatası C2482
ms.date: 09/15/2017
f1_keywords:
- C2482
helpviewer_keywords:
- C2482
ms.assetid: 98c87da2-625c-4cc2-9bf7-78d15921e779
ms.openlocfilehash: 5afa81369b2cf329baae02bc1309587015946409
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80205159"
---
# <a name="compiler-error-c2482"></a>Derleyici hatası C2482

>'*tanımlayıcı*': yönetilen/WinRT kodunda ' Thread ' verilerinin dinamik olarak başlatılmasına izin verilmiyor

## <a name="remarks"></a>Açıklamalar

Yönetilen veya WinRT kodunda, [__declspec (thread)](../../cpp/thread.md) depolama sınıfı değiştirici özniteliği veya [thread_local](../../cpp/storage-classes-cpp.md#thread_local) depolama sınıfı Belirleyicisi kullanılarak belirtilen değişkenler, çalışma zamanında değerlendirme gerektiren bir ifadeyle başlatılamaz. Bu çalışma zamanı ortamlarında `__declspec(thread)` veya `thread_local` verileri başlatmak için statik bir ifade gerekir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, yönetilen ( **/clr**) ve WinRT ( **/ZW**) kodunda C2482 oluşturur:

```cpp
// C2482.cpp
// For managed example, compile with: cl /EHsc /c /clr C2482.cpp
// For WinRT example, compile with: cl /EHsc /c /ZW C2482.cpp
#define Thread __declspec( thread )
Thread int tls_i1 = tls_i1;   // C2482

int j = j;   // OK in C++; C error
Thread int tls_i2 = sizeof( tls_i2 );   // Okay in C and C++
```

Bu sorunu onarmak için, sabit, **constexpr**veya statik bir ifade kullanarak iş parçacığı yerel depolamayı başlatın. Her iş parçacığına özgü başlatmayı ayrı olarak gerçekleştirin.
