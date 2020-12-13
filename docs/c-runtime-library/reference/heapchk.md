---
description: 'Hakkında daha fazla bilgi edinin: _heapchk'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 57cde789c8d6e6b8c8da91adf4a6f274ce557ed7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332798"
---
# <a name="_heapchk"></a>_heapchk

Yığın üzerinde tutarlılık denetimleri çalıştırır.

## <a name="syntax"></a>Syntax

```C
int _heapchk( void );
```

## <a name="return-value"></a>Dönüş Değeri

**_heapchk** , malloc. h içinde tanımlanan aşağıdaki tamsayı bildirimi sabitlerinden birini döndürür.

|Döndürülen değer|Koşul|
|-|-|
| **_HEAPBADBEGIN** | İlk üstbilgi bilgisi hatalı veya bulunamıyor. |
| **_HEAPBADNODE** | Hatalı düğüm bulundu veya yığın hasarlı. |
| **_HEAPBADPTR** | Yığında işaretçi geçerli değil. |
| **_HEAPEMPTY** | Yığın başlatılmamış. |
| **_HEAPOK** | Yığın tutarlı görünüyor. |

Buna ek olarak, bir hata oluşursa **_heapchk** **errno** , **ENOSYS** olarak ayarlanır.

## <a name="remarks"></a>Açıklamalar

**_Heapchk** işlevi, yığının en az tutarlılığını denetleyerek yığında ilgili sorunları ayıklamanıza yardımcı olur. İşletim sistemi **_heapchk**(örneğin, Windows 98) desteklemiyorsa, işlev **_HEAPOK** döndürür ve **errno** , **ENOSYS** olarak ayarlar.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_heapchk**|\<malloc.h>|\<errno.h>|

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

[Bellek ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[_heapadd](../../c-runtime-library/heapadd.md)<br/>
[_heapmin](heapmin.md)<br/>
[_heapset](../../c-runtime-library/heapset.md)<br/>
[_heapwalk](heapwalk.md)<br/>
