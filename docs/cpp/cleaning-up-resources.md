---
title: Kaynakları Temizleme
ms.date: 11/04/2016
helpviewer_keywords:
- termination handlers [C++], cleaning up resources
- exception handling [C++], cleaning up resources
- C++ exception handling, termination handlers
- resources [C++], cleaning up
- exception handling [C++], cleanup code
- try-catch keyword [C++], termination handlers
ms.assetid: 65753efe-6a27-4750-b90c-50635775c1b6
ms.openlocfilehash: 225c3ccaf3342f11ad4eb6d6575ad3ac542acfd2
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246642"
---
# <a name="cleaning-up-resources"></a>Kaynakları Temizleme

Sonlandırma işleyicisi yürütülürken, sonlandırma işleyicisi çağrılmadan önce hangi kaynakların gerçekten ayrıldığını bilemeyebilirsiniz. Tüm kaynaklar ayrılmadan önce **__try** ekstre bloğunun kesintiye uğratıldığından, tüm kaynakların açılmaması mümkündür.

Bu nedenle, güvende olmak için, sonlandırma işleme temizleme işlemine devam etmeden önce hangi kaynakların açık olduğunu görmek için denetlemelisiniz. Önerilen bir yordam şöyledir:

1. Tanıtıcıları NULL olarak başlatın.

1. **__Try** bildiri bloğunda, kaynak ayırın. Kaynak ayırma işlemi yapılırken tanıtıcılar pozitif değerlere ayarlanır.

1. **__Finally** bildiri bloğunda, karşılık gelen tanıtıcı veya bayrak değişkeni sıfır olmayan veya null olmayan her kaynağı serbest bırakın.

## <a name="example"></a>Örnek

Örneğin, aşağıdaki kod, üç dosyayı ve **__try** bildiri bloğunda ayrılan bir bellek bloğunu kapatmak için bir sonlandırma işleyicisi kullanır. Kod, bir kaynağı silmeden önce kaynağın ayrılıp ayrılmadığını kontrol eder.

```cpp
// exceptions_Cleaning_up_Resources.cpp
#include <stdlib.h>
#include <malloc.h>
#include <stdio.h>
#include <windows.h>

void fileOps() {
   FILE  *fp1 = NULL,
         *fp2 = NULL,
         *fp3 = NULL;
   LPVOID lpvoid = NULL;
   errno_t err;

   __try {
      lpvoid = malloc( BUFSIZ );

      err = fopen_s(&fp1, "ADDRESS.DAT", "w+" );
      err = fopen_s(&fp2, "NAMES.DAT", "w+" );
      err = fopen_s(&fp3, "CARS.DAT", "w+" );
   }
   __finally {
      if ( fp1 )
         fclose( fp1 );
      if ( fp2 )
         fclose( fp2 );
      if ( fp3 )
         fclose( fp3 );
      if ( lpvoid )
         free( lpvoid );
   }
}

int main() {
   fileOps();
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Sonlandırma işleyicisi yazma](../cpp/writing-a-termination-handler.md)<br/>
[Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)