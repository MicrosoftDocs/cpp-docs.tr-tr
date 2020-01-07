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
ms.openlocfilehash: c47ab59b1d8b9e73add640f7a7cf5fb146dc7c53
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75300267"
---
# <a name="_heapset"></a>_heapset

Yığınlarını en düşük tutarlılık açısından denetler ve ücretsiz girdileri belirtilen bir değere ayarlar.

> [!IMPORTANT]
>  Bu işlev artık kullanılmıyor. Visual Studio 2015 ' den başlayarak CRT ' de kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
int _heapset(
   unsigned int fill
);
```

#### <a name="parameters"></a>Parametreler

*doldurması*<br/>
Karakteri doldur.

## <a name="return-value"></a>Dönüş Değeri

`_heapset`, malloc. h içinde tanımlanan aşağıdaki tamsayı bildirimi sabitlerinden birini döndürür.

|||
|-|-|
| `_HEAPBADBEGIN`  | İlk üstbilgi bilgisi geçersiz veya bulunamadı.  |
| `_HEAPBADNODE`  | Yığın hasarlı veya hatalı düğüm bulundu.  |
| `_HEAPEMPTY`  | Yığın başlatılmadı.  |
| `_HEAPOK`  | Yığın tutarlı görünüyor.  |

Ayrıca, bir hata oluşursa `_heapset` `errno` `ENOSYS`olarak ayarlar.

## <a name="remarks"></a>Açıklamalar

`_heapset` işlevi, yanlışlıkla üzerine yazılan boş bellek konumlarını veya düğümlerini gösterir.

`_heapset` yığın üzerinde en az tutarlılığı denetler ve sonra yığının boş girişlerinin her baytını `fill` değerine ayarlar. Bu bilinen değer, yığında serbest düğüm ve yanlışlıkla serbest bırakılmış belleğe yazılan verileri içeren hangi bellek konumlarının olduğunu gösterir. İşletim sistemi `_heapset`(örneğin, Windows 98) desteklemiyorsa, işlev `_HEAPOK` döndürür ve `errno` `ENOSYS`olarak ayarlar.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|`_heapset`|\<malloc. h >|\<errno. h >|

Daha fazla uyumluluk bilgisi için bkz. karşılama 'da [Uyumluluk](../c-runtime-library/compatibility.md) .

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
