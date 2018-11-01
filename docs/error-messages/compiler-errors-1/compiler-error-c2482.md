---
title: Derleyici Hatası C2482
ms.date: 09/15/2017
f1_keywords:
- C2482
helpviewer_keywords:
- C2482
ms.assetid: 98c87da2-625c-4cc2-9bf7-78d15921e779
ms.openlocfilehash: 481920fa2d8c32bc872e7b8805188cc674e6fe28
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50564820"
---
# <a name="compiler-error-c2482"></a>Derleyici Hatası C2482

>'*tanımlayıcı*': dinamik başlatma yönetilen WinRT kodunda izin verilmez 'thread' veri

## <a name="remarks"></a>Açıklamalar

İçinde yönetilen veya WinRT kodu, değişkenleri kullanılarak bildirilen [gt;__declspec(thread)](../../cpp/thread.md) depolama sınıfı değiştiricisi özniteliği veya [thread_local](../../cpp/storage-classes-cpp.md#thread_local) depolama sınıfı tanımlayıcısı bir ifade ile başlatılamaz Değerlendirme çalışma zamanında gerektirir. Statik bir ifade başlatmak için gerekli `__declspec(thread)` veya `thread_local` bu çalışma zamanı ortamlarını verileri.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2482 oluşturur yönetilen (**/CLR**) ve WinRT (**/ZW**) kodu:

```cpp
// C2482.cpp
// For managed example, compile with: cl /EHsc /c /clr C2482.cpp
// For WinRT example, compile with: cl /EHsc /c /ZW C2482.cpp
#define Thread __declspec( thread )
Thread int tls_i1 = tls_i1;   // C2482

int j = j;   // OK in C++; C error
Thread int tls_i2 = sizeof( tls_i2 );   // Okay in C and C++
```

Bu sorunu gidermek için iş parçacığı-yerel depolamayı bir sabit'ı kullanarak başlatmak için **constexpr**, veya statik bir ifade. Herhangi bir iş parçacığına özgü başlatma ayrı olarak gerçekleştirin.