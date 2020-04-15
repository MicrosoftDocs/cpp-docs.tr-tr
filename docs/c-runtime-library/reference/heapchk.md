---
title: _heapchk
ms.date: 4/2/2020
api_name:
- _heapchk
- _o__heapchk
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-heap-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _heapchk
- heapchk
helpviewer_keywords:
- debugging [CRT], heap-related problems
- consistency checking of heaps
- heapchk function
- heaps, checking consistency
- _heapchk function
ms.assetid: 859619a5-1e35-4f02-9e09-11d9fa266ec0
ms.openlocfilehash: 21c7f9e22728109676d3fc611405ccd43ac773f8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344055"
---
# <a name="_heapchk"></a>_heapchk

Yığınüzerinde tutarlılık denetimleri çalıştırın.

## <a name="syntax"></a>Sözdizimi

```C
int _heapchk( void );
```

## <a name="return-value"></a>Dönüş Değeri

**_heapchk,** Malloc.h'de tanımlanan aşağıdaki tamsayı bildirim sabitlerinden birini döndürür.

|Döndürülen değer|Koşul|
|-|-|
| **_HEAPBADBEGIN** | İlk üstbilgi bilgileri bozuk veya bulunamıyor. |
| **_HEAPBADNODE** | Kötü düğüm bulundu veya yığın zarar gördü. |
| **_HEAPBADPTR** | İşaretçi yığına geçerli değildir. |
| **_HEAPEMPTY** | Yığın başharfe bünyedi değil. |
| **_HEAPOK** | Yığın tutarlı görünüyor. |

Buna ek olarak, bir hata oluşursa, **_heapchk** **ENOSYS** **için errno** ayarlar.

## <a name="remarks"></a>Açıklamalar

**_heapchk** işlevi, yığının en az tutarlılığını denetleyerek yığınla ilgili sorunları ayıklamanıza yardımcı olur. İşletim sistemi **_heapchk**(örneğin, Windows 98) desteklemiyorsa, işlev **_HEAPOK** döndürür ve **errno'yu** **ENOSYS'e**ayarlar.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|**_heapchk**|\<malloc.h>|\<errno.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_heapchk.c
// This program checks the heap for
// consistency and prints an appropriate message.

#include <malloc.h>
#include <stdio.h>

int main( void )
{
   int  heapstatus;
   char *buffer;

   // Allocate and deallocate some memory
   if( (buffer = (char *)malloc( 100 )) != NULL )
      free( buffer );

   // Check heap status
   heapstatus = _heapchk();
   switch( heapstatus )
   {
   case _HEAPOK:
      printf(" OK - heap is fine\n" );
      break;
   case _HEAPEMPTY:
      printf(" OK - heap is empty\n" );
      break;
   case _HEAPBADBEGIN:
      printf( "ERROR - bad start of heap\n" );
      break;
   case _HEAPBADNODE:
      printf( "ERROR - bad node in heap\n" );
      break;
   }
}
```

```Output
OK - heap is fine
```

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[_heapadd](../../c-runtime-library/heapadd.md)<br/>
[_heapmin](heapmin.md)<br/>
[_heapset](../../c-runtime-library/heapset.md)<br/>
[_heapwalk](heapwalk.md)<br/>
