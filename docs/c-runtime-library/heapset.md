---
title: _heapset
ms.date: 11/04/2016
apiname:
- _heapset
apilocation:
- msvcr90.dll
- msvcr80.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr120.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- _heapset
- heapset
helpviewer_keywords:
- checking heap
- heapset function
- heaps, checking
- debugging [CRT], heap-related problems
- _heapset function
ms.assetid: 9667eeb0-55bc-4c19-af5f-d1fd0a142b3c
ms.openlocfilehash: c93624b8b56fb53eb15263dbd0d203cd9130eacf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50528199"
---
# <a name="heapset"></a>_heapset

En az tutarlılık yığınlar denetler ve ücretsiz girişler için belirtilen değere ayarlar.

> [!IMPORTANT]
>  Bu işlev artık kullanılmıyor. Visual Studio 2015'te başlayarak, CRT içinde kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
int _heapset(
   unsigned int fill
);
```

#### <a name="parameters"></a>Parametreler

*Dolgu*<br/>
Karakter girin.

## <a name="return-value"></a>Dönüş Değeri

`_heapset` Malloc.h içinde tanımlı aşağıdaki tam sayı bildirim sabitlerinden birini döndürür.

|||
|-|-|
| `_HEAPBADBEGIN`  | İlk üstbilgi bilgileri geçersiz veya bulunamadı.  |
| `_HEAPBADNODE`  | Yığın zarar görmüş veya bozuk düğümü bulunamadı.  |
| `_HEAPEMPTY`  | Yığın başlatılmadı.  |
| `_HEAPOK`  | Yığın tutarlı görünüyor.  |

Ayrıca, bir hata oluşursa `_heapset` ayarlar `errno` için `ENOSYS`.

## <a name="remarks"></a>Açıklamalar

`_heapset` İşlevi boş bellek konumları veya yanlışlıkla üzerine olan düğümleri gösterir.

`_heapset` Yığındaki en alt düzeyde tutarlılık olup olmadığını denetler ve ardından yığının ücretsiz girişine ait her baytın ayarlar `fill` değeri. Bu bilinen değer, hangi yığın bellek konumları ücretsiz düğümler içerebilir ve serbest bırakılan belleğe yanlışlıkla yazılmış veri içerir gösterir. İşletim sistemi desteklemiyorsa `_heapset`(örneğin, Windows 98), işlev döndürür `_HEAPOK` ve ayarlar `errno` için `ENOSYS`.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|`_heapset`|\<malloc.h >|\<errno.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../c-runtime-library/compatibility.md) giriş.

## <a name="example"></a>Örnek

```
// crt_heapset.c
// This program checks the heap and
// fills in free entries with the character 'Z'.

#include <malloc.h>
#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   int heapstatus;
   char *buffer;

   if( (buffer = malloc( 1 )) == NULL ) // Make sure heap is
      exit( 0 );                        //    initialized
   heapstatus = _heapset( 'Z' );        // Fill in free entries
   switch( heapstatus )
   {
   case _HEAPOK:
      printf( "OK - heap is fine\n" );
      break;
   case _HEAPEMPTY:
      printf( "OK - heap is empty\n" );
      break;
   case _HEAPBADBEGIN:
      printf( "ERROR - bad start of heap\n" );
      break;
   case _HEAPBADNODE:
      printf( "ERROR - bad node in heap\n" );
      break;
   }
   free( buffer );
}
```

```Output
OK - heap is fine
```

## <a name="see-also"></a>Ayrıca Bkz.

[Bellek Ayırma](../c-runtime-library/memory-allocation.md)<br/>
[_heapadd](../c-runtime-library/heapadd.md)<br/>
[_heapchk](../c-runtime-library/reference/heapchk.md)<br/>
[_heapmin](../c-runtime-library/reference/heapmin.md)<br/>
[_heapwalk](../c-runtime-library/reference/heapwalk.md)