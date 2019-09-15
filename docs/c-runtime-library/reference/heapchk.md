---
title: _heapchk
ms.date: 11/04/2016
api_name:
- _heapchk
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
ms.openlocfilehash: 857feb66d89d5dc406042478156483ecb86a2474
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70954821"
---
# <a name="_heapchk"></a>_heapchk

Yığın üzerinde tutarlılık denetimleri çalıştırır.

## <a name="syntax"></a>Sözdizimi

```C
int _heapchk( void );
```

## <a name="return-value"></a>Dönüş Değeri

**_heapchk** , malloc. h içinde tanımlanan aşağıdaki tamsayı bildirimi sabitlerinden birini döndürür.

|Dönüş değeri|Koşul|
|-|-|
| **_HEAPBADBEGIN** | İlk üstbilgi bilgisi hatalı veya bulunamıyor. |
| **_HEAPBADNODE** | Hatalı düğüm bulundu veya yığın hasarlı. |
| **_HEAPBADPTR** | Yığında işaretçi geçerli değil. |
| **_HEAPEMPTY** | Yığın başlatılmamış. |
| **_CENPOK** | Yığın tutarlı görünüyor. |

Buna ek olarak, bir hata oluşursa, **_heapchk** , **errno** , **ENOSYS**olarak ayarlar.

## <a name="remarks"></a>Açıklamalar

**_Heapchk** Function, yığının en az tutarlılığını denetleyerek yığın ile ilgili sorunların hatalarını ayıklamasına yardımcı olur. İşletim sistemi **_heapchk**'yi (örneğin, Windows 98) desteklemiyorsa, Işlev **_Cenpok** döndürür ve **errno** değerini **ENOSYS**olarak ayarlar.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_heapchk**|\<malloc. h >|\<errno. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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
