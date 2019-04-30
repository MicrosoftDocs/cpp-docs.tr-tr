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
ms.openlocfilehash: 0db21b20b94dc1a3f347bd848c999a961398759b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386128"
---
# <a name="cleaning-up-resources"></a>Kaynakları Temizleme

Sonlandırma işleyicisi yürütülürken, sonlandırma işleyicisi çağrılmadan önce hangi kaynakların gerçekten ayrıldığını bilemeyebilirsiniz. Mümkünse, **__try** deyim bloğunun durdurulması tüm kaynaklar ayrılmadan önce böylece tüm kaynaklar açılmaz.

Bu nedenle, güvende olmak için, sonlandırma işleme temizleme işlemine devam etmeden önce hangi kaynakların açık olduğunu görmek için denetlemelisiniz. Önerilen bir yordam şöyledir:

1. Tanıtıcıları NULL olarak başlatın.

1. İçinde **__try** deyimi engelleme, kaynakları ayırın. Kaynak ayırma işlemi yapılırken tanıtıcılar pozitif değerlere ayarlanır.

1. İçinde **__finally** deyim bloğunda, karşılık gelen tanıtıcısı veya bayrak değişkeni sıfır olmayan her kaynağı serbest bırakın veya not NULL.

## <a name="example"></a>Örnek

Örneğin, aşağıdaki kod üç dosyayı ve ayrılmış bir bellek bloğunu kapatmak için bir sonlandırma işleyicisi kullanır **__try** deyim bloğu. Kod, bir kaynağı silmeden önce kaynağın ayrılıp ayrılmadığını kontrol eder.

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

[Sonlandırma İşleyicisi Yazma](../cpp/writing-a-termination-handler.md)<br/>
[Yapılandırılmış Özel Durum İşleme (C/C++)](../cpp/structured-exception-handling-c-cpp.md)