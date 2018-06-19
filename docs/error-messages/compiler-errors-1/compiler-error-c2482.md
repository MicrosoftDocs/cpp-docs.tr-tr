---
title: Derleyici Hatası C2482 | Microsoft Docs
ms.custom: ''
ms.date: 09/15/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2482
dev_langs:
- C++
helpviewer_keywords:
- C2482
ms.assetid: 98c87da2-625c-4cc2-9bf7-78d15921e779
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c3dd23069f389d0a02e10d26edb7ee4fd3c373cb
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34256012"
---
# <a name="compiler-error-c2482"></a>Derleyici Hatası C2482

>'*tanımlayıcısı*': 'iş parçacığı' veri yönetilen WinRT kod içinde izin verilmiyor dinamik başlatma

## <a name="remarks"></a>Açıklamalar

İçinde yönetilen veya bir kod WinRT, kullanarak bildirilen değişkenlerin [__declspec(thread)](../../cpp/thread.md) depolama sınıfı değiştirici özniteliği veya [thread_local](../../cpp/storage-classes-cpp.md#thread_local) depolama sınıfı tanımlayıcısı sahip bir ifade başlatılamıyor Çalışma zamanında değerlendirme gerektirir. Statik bir ifade başlatmak için gerekli `__declspec(thread)` veya `thread_local` bu çalışma zamanı ortamları verileri.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2482 oluşturur yönetilen (**/CLR**) ve WinRT (**/ZW**) kod:

```cpp
// C2482.cpp
// For managed example, compile with: cl /EHsc /c /clr C2482.cpp
// For WinRT example, compile with: cl /EHsc /c /ZW C2482.cpp
#define Thread __declspec( thread )
Thread int tls_i1 = tls_i1;   // C2482

int j = j;   // OK in C++; C error
Thread int tls_i2 = sizeof( tls_i2 );   // Okay in C and C++
```

Bu sorunu gidermek için bir sabit kullanarak iş parçacığı yerel depolama başlatmak **constexpr**, ya da statik ifade. Tüm iş parçacığına özgü başlatma ayrı olarak gerçekleştirir.