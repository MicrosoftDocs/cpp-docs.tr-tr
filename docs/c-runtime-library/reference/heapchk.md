---
title: _heapchk
ms.date: 11/04/2016
apiname:
- _heapchk
apilocation:
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
apitype: DLLExport
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
ms.openlocfilehash: bdc0137761664a668d6ef95d739f09501e8290e5
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51331405"
---
# <a name="heapchk"></a>_heapchk

Yığın üzerinde tutarlılık denetimleri çalıştırır.

## <a name="syntax"></a>Sözdizimi

```C
int _heapchk( void );
```

## <a name="return-value"></a>Dönüş Değeri

**_heapchk** Malloc.h içinde tanımlı aşağıdaki tam sayı bildirim sabitlerinden birini döndürür.

|Dönüş değeri|Koşul|
|-|-|
| **_HEAPBADBEGIN** | İlk üstbilgi bilgileri hatalı veya bulunamıyor. |
| **_HEAPBADNODE** | Yığın zarar ya da bozuk düğümü bulundu. |
| **_HEAPBADPTR** | Yığın halinde işaretçi geçerli değil. |
| **_HEAPEMPTY** | Yığın başlatılmadı. |
| **_HEAPOK** | Yığın tutarlı görünüyor. |

Ayrıca, bir hata oluşursa **_heapchk** ayarlar **errno** için **ENOSYS**.

## <a name="remarks"></a>Açıklamalar

**_Heapchk** işlevi, en düşük öbek tutarlılık açısından denetleyerek yığınla ilişkili sorunlarda hata ayıklama yardımcı olur. İşletim sistemi desteklemiyorsa **_heapchk**(örneğin, Windows 98), işlev döndürür **_HEAPOK** ve ayarlar **errno** için **ENOSYS**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_heapchk**|\<malloc.h >|\<errno.h >|

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
