---
title: _Crtısvalidheappointer | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtIsValidHeapPointer
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
apitype: DLLExport
f1_keywords:
- CrtlsValidHeapPointer
- _CrtIsValidHeapPointer
dev_langs:
- C++
helpviewer_keywords:
- _CrtIsValidHeapPointer function
- CrtIsValidHeapPointer function
ms.assetid: caf597ce-1b05-4764-9f37-0197a982bec5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1bc4be3f464cb48647985a96550a8b9ea13ce5ef
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32396699"
---
# <a name="crtisvalidheappointer"></a>_CrtIsValidHeapPointer

Belirtilen bir işaretçi bazı C çalışma zamanı kitaplığı, ancak mutlaka tarafından arayanın CRT kitaplık ayrılmış yığın olduğunu doğrular. Visual Studio 2010 önce CRT sürümlerinde, bu belirtilen işaretçi yerel yığın (yalnızca hata ayıklama sürümü) olduğunu doğrular.

## <a name="syntax"></a>Sözdizimi

```C
int _CrtIsValidHeapPointer(
   const void *userData
);
```

### <a name="parameters"></a>Parametreler

*UserData*<br/>
Ayrılmış bellek bloğu başlangıcı işaretçi.

## <a name="return-value"></a>Dönüş Değeri

**_Crtısvalidheappointer** tüm CRT kitaplık örnekleri tarafından paylaşılan yığın belirtilen işaretçidir varsa TRUE değerini döndürür. Visual Studio 2010 önce CRT sürümlerinde, belirtilen işaretçi yerel yığınında ise bu TRUE döndürür. Aksi takdirde işlevi FALSE değerini döndürür.

## <a name="remarks"></a>Açıklamalar

Bu işlev kullanmanızı önermiyoruz. Visual Studio 2010 CRT kitaplık ile başlayarak, bir işletim sistemi yığın tüm CRT kitaplıkları paylaşma *işlem yığın*. **_Crtısvalidheappointer** işlevi işaretçiyi CRT yığınında arayanın CRT kitaplık tarafından ayrılan ayrıldı ancak olup olmadığını bildirir. Örneğin, CRT kitaplık Visual Studio 2010 sürümü kullanılarak ayrılmış bir blok göz önünde bulundurun. Varsa **_crtısvalidheappointer** CRT kitaplık Visual Studio 2012 sürümü tarafından dışarı aktarılan işlevin işaretçinin testleri, TRUE döndürür. Bu artık yararlı bir denemedir. Visual Studio 2010 önce CRT kitaplık sürümlerinde işlevi belirli bellek adresi yerel yığın içinde olduğundan emin olmak için kullanılır. Yerel yığın oluşturulur ve C çalışma zamanı kitaplığı belirli bir örneği tarafından yönetilen yığın ifade eder. Dinamik bağlantı kitaplığı (DLL) çalışma zamanı kitaplığı için statik bir bağlantı içeriyorsa, çalışma zamanı öbek ve bu nedenle, uygulamanın yerel yığın bağımsız kendi yığın kendi örneğine sahip. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar **_crtısvalidheappointer** ön işleme sırasında kaldırılır.

Bu işlev TRUE veya false değeri döndürdüğünden, aşağıdakilerden birini geçirilebilir [_ASSERT](assert-asserte-assert-expr-macros.md) makroları işleme mekanizması basit bir hata ayıklama hata oluştur. Belirtilen adres yerel yığın içinde bulunduğu değilse, aşağıdaki örnekte bir onaylama işlemi hatasına neden olur:

```C
_ASSERTE( _CrtIsValidHeapPointer( userData ) );
```

Hakkında daha fazla bilgi için **_crtısvalidheappointer** diğer hata ayıklama işlevleri ve makrolar kullanılabilmesi için bkz: [raporlama makroları](/visualstudio/debugger/macros-for-reporting). Nasıl bellek blokları ayrılmış, başlatılmış ve temel yığın hata ayıklama sürümü yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtIsValidHeapPointer**|\<crtdbg.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="example"></a>Örnek

Aşağıdaki örnek, Visual Studio 2010 önce C çalışma zamanı kitaplıkları ile kullanıldığında bellek geçerli olup olmadığını sınamak gösterilmiştir. Bu örnekte, eski CRT kitaplık kodu kullanıcılar için sağlanır.

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

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
