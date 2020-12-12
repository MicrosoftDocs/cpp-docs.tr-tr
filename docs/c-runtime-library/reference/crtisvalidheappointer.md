---
description: 'Hakkında daha fazla bilgi edinin: _CrtIsValidHeapPointer'
title: _CrtIsValidHeapPointer
ms.date: 11/04/2016
api_name:
- _CrtIsValidHeapPointer
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- CrtlsValidHeapPointer
- _CrtIsValidHeapPointer
helpviewer_keywords:
- _CrtIsValidHeapPointer function
- CrtIsValidHeapPointer function
ms.assetid: caf597ce-1b05-4764-9f37-0197a982bec5
ms.openlocfilehash: 71a281cdf63ad1c37162da1b1be099764085f739
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319709"
---
# <a name="_crtisvalidheappointer"></a>_CrtIsValidHeapPointer

Belirtilen bir işaretçinin bazı C çalışma zamanı kitaplığı tarafından ayrılan, ancak çağıranın CRT kitaplığı tarafından atanan bir yığında olduğunu doğrular. Visual Studio 2010 ' den önceki CRT sürümlerinde, bu, belirtilen işaretçinin yerel yığında olduğunu doğrular (yalnızca hata ayıklama sürümü).

## <a name="syntax"></a>Sözdizimi

```C
int _CrtIsValidHeapPointer(
   const void *userData
);
```

### <a name="parameters"></a>Parametreler

*userData*<br/>
Ayrılmış bellek bloğunun başlangıcına yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

**_CrtIsValidHeapPointer** , belirtilen IŞARETÇI tüm CRT kitaplık örnekleri tarafından paylaşılan yığında yer alıyorsa true değerini döndürür. Visual Studio 2010 ' den önceki CRT sürümlerinde, belirtilen işaretçi yerel yığında ise TRUE değeri döndürür. Aksi takdirde, işlev FALSE döndürür.

## <a name="remarks"></a>Açıklamalar

Bu işlevi kullanmanızı önermiyoruz. Visual Studio 2010 CRT kitaplığı ile başlayarak, tüm CRT kitaplıkları bir işletim sistemi yığını, *işlem yığını* paylaşır. **_CrtIsValidHeapPointer** işlevi, IŞARETÇININ bir CRT yığınında ayrıldığını, ancak çağıranın CRT kitaplığı tarafından ayrılmadığını bildirir. Örneğin, CRT kitaplığı 'nın Visual Studio 2010 sürümünü kullanarak ayrılmış bir bloğu düşünün. CRT kitaplığı 'nın Visual Studio 2012 sürümü tarafından aktarılmış **_CrtIsValidHeapPointer** işlevi işaretçiyi test eder, true döndürür. Bu artık yararlı bir test değildir. Visual Studio 2010 ' den önceki CRT kitaplığı sürümlerinde, belirli bir bellek adresinin yerel yığın dahilinde olduğundan emin olmak için işlevi kullanılır. Yerel yığın, C çalışma zamanı kitaplığının belirli bir örneği tarafından oluşturulan ve yönetilen yığına başvurur. Dinamik bağlantı kitaplığı (DLL) çalışma zamanı kitaplığına statik bir bağlantı içeriyorsa, çalışma zamanı yığınının kendi örneğine ve bu nedenle uygulamanın yerel yığınından bağımsız olarak kendi yığınına sahiptir. [_DEBUG](../../c-runtime-library/debug.md) tanımlı olmadığında, **_CrtIsValidHeapPointer** çağrıları ön işleme sırasında kaldırılır.

Bu işlev TRUE veya FALSE döndürdüğünden, basit bir hata ayıklama hata işleme mekanizması oluşturmak için [_assert](assert-asserte-assert-expr-macros.md) makrolarından birine geçirilebilir. Aşağıdaki örnek, belirtilen adres yerel yığında bulunmuyorsa bir onaylama hatasına neden olur:

```C
_ASSERTE( _CrtIsValidHeapPointer( userData ) );
```

**_CrtIsValidHeapPointer** diğer hata ayıklama işlevleri ve makroları ile nasıl kullanılabileceği hakkında daha fazla bilgi için bkz. about [Macros](/visualstudio/debugger/macros-for-reporting). Bellek bloklarının taban yığının hata ayıklama sürümünde nasıl ayrıldığı, başlatıldığı ve yönetildiği hakkında bilgi için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtIsValidHeapPointer**|\<crtdbg.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, Visual Studio 2010 ' den önceki C çalışma zamanı kitaplıkları ile kullanıldığında belleğin geçerli olup olmadığını nasıl test etmek gerektiğini gösterir. Bu örnek, eski CRT kitaplığı kodu kullanıcıları için verilmiştir.

```C
// crt_isvalid.c
// This program allocates a block of memory using _malloc_dbg
// and then tests the validity of this memory by calling
// _CrtIsMemoryBlock,_CrtIsValidPointer, and _CrtIsValidHeapPointer.

#include <stdio.h>
#include <string.h>
#include <malloc.h>
#include <crtdbg.h>

#define  TRUE   1
#define  FALSE  0

int main( void )
{
    char *my_pointer;

    // Call _malloc_dbg to include the filename and line number
    // of our allocation request in the header information
    my_pointer = (char *)_malloc_dbg( sizeof(char) * 10,
        _NORMAL_BLOCK, __FILE__, __LINE__ );

    // Ensure that the memory got allocated correctly
    _CrtIsMemoryBlock((const void *)my_pointer, sizeof(char) * 10,
        NULL, NULL, NULL );

    // Test for read/write accessibility
    if (_CrtIsValidPointer((const void *)my_pointer,
        sizeof(char) * 10, TRUE))
        printf("my_pointer has read and write accessibility.\n");
    else
        printf("my_pointer only has read access.\n");

    // Make sure my_pointer is within the local heap
    if (_CrtIsValidHeapPointer((const void *)my_pointer))
        printf("my_pointer is within the local heap.\n");
    else
        printf("my_pointer is not located within the local"
               " heap.\n");

    free(my_pointer);
}
```

```Output
my_pointer has read and write accessibility.
my_pointer is within the local heap.
```

## <a name="see-also"></a>Ayrıca bkz.

[Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)<br/>
