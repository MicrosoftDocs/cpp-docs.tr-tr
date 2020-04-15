---
title: _heapset
ms.date: 11/04/2016
api_name:
- _heapset
api_location:
- msvcr90.dll
- msvcr80.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr120.dll
- msvcr100.dll
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 2a0aea37237f04939579eb059a42dd33771339ad
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81351267"
---
# <a name="_heapset"></a>_heapset

Yığınları en az tutarlılık için denetler ve boş girişleri belirli bir değere ayarlar.

> [!IMPORTANT]
> Bu işlev geçersizdir. Visual Studio 2015'ten itibaren CRT'de kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
int _heapset(
   unsigned int fill
);
```

#### <a name="parameters"></a>Parametreler

*fill*<br/>
Karakteri doldurun.

## <a name="return-value"></a>Dönüş Değeri

`_heapset`Malloc.h'de tanımlanan aşağıdaki sondalı bildirim sabitlerinden birini döndürür.

|||
|-|-|
| `_HEAPBADBEGIN`  | İlk üstbilgi bilgileri geçersiz veya bulunamadı.  |
| `_HEAPBADNODE`  | Yığın hasarlı veya kötü düğüm bulundu.  |
| `_HEAPEMPTY`  | Yığın başharfe bünyede değil.  |
| `_HEAPOK`  | Yığın tutarlı görünüyor.  |

Buna ek olarak, bir `_heapset` hata `errno` `ENOSYS`oluşursa, ayarlar.

## <a name="remarks"></a>Açıklamalar

İşlev, `_heapset` istemeden üzerine yazılmış boş bellek konumlarını veya düğümlerini gösterir.

`_heapset`yığında en az tutarlılığı denetler ve sonra yığının boş girişlerinin `fill` her bir baytını değere ayarlar. Bu bilinen değer, yığının hangi bellek konumlarının boş düğümler içerdiğini ve serbest bırakılan belleğe istemeden yazılmış verileri içeren verileri gösterir. İşletim sistemi `_heapset`desteklemiyorsa (örneğin, Windows 98), işlev döndürür `_HEAPOK` ve `errno` . `ENOSYS`

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|`_heapset`|\<malloc.h>|\<errno.h>|

Daha fazla uyumluluk bilgisi için Giriş'te [Uyumluluk'a](../c-runtime-library/compatibility.md) bakın.

## <a name="example"></a>Örnek

```c
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

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../c-runtime-library/memory-allocation.md)<br/>
[_heapadd](../c-runtime-library/heapadd.md)<br/>
[_heapchk](../c-runtime-library/reference/heapchk.md)<br/>
[_heapmin](../c-runtime-library/reference/heapmin.md)<br/>
[_heapwalk](../c-runtime-library/reference/heapwalk.md)
