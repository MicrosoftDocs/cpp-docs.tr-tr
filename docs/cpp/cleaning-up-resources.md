---
title: Kaynakları temizleme
description: Yapılandırılmış özel durum işleme için sonlandırma işleyicisi sırasında kaynakları serbest bırakma.
ms.date: 08/24/2020
helpviewer_keywords:
- termination handlers [C++], cleaning up resources
- exception handling [C++], cleaning up resources
- C++ exception handling, termination handlers
- resources [C++], cleaning up
- exception handling [C++], cleanup code
- try-catch keyword [C++], termination handlers
ms.assetid: 65753efe-6a27-4750-b90c-50635775c1b6
ms.openlocfilehash: dae92a515db25b9985a890d7d08cc213f88ecfea
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898441"
---
# <a name="cleaning-up-resources"></a>Kaynakları temizleme

Sonlandırma işleyicisi yürütmesi sırasında, sonlandırma işleyicisi çağrılmadan önce hangi kaynakların edinildiği bilinmiyor olabilir. Tüm kaynaklar **`__try`** alınmadan önce ekstre bloğunun kesintiye uğratıldığından, tüm kaynakların açılmaması mümkündür.

Güvenli olması için, sonlandırma işleme ile devam etmeden önce hangi kaynakların açık olduğunu görmeniz gerekir. Önerilen bir yordam şöyledir:

1. Tanıtıcıları NULL olarak başlatın.

1. **`__try`** Ekstre bloğunda, kaynak alın. Kaynak alındığından, tutamaçlar pozitif değerler olarak ayarlanır.

1. **`__finally`** Ekstre bloğunda, karşılık gelen tanıtıcı veya bayrak değişkeni sıfır olmayan veya null olmayan her kaynağı serbest bırakın.

## <a name="example"></a>Örnek

Örneğin, aşağıdaki kod, üç dosyayı kapatmak ve bir bellek bloğunu serbest bırakmak için bir sonlandırma işleyicisi kullanır. Bu kaynaklar, **`__try`** Ekstre bloğunda alındı. Bir kaynağı temizlemeden önce, kod ilk olarak kaynağın elde olup olmadığını denetler.

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
