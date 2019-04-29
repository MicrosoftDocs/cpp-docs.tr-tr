---
title: _CrtIsValidHeapPointer
ms.date: 11/04/2016
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
helpviewer_keywords:
- _CrtIsValidHeapPointer function
- CrtIsValidHeapPointer function
ms.assetid: caf597ce-1b05-4764-9f37-0197a982bec5
ms.openlocfilehash: cdfb02c622cddc4c86a99f614e469abc527d8845
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62339396"
---
# <a name="crtisvalidheappointer"></a>_CrtIsValidHeapPointer

Bazı C çalışma zamanı kitaplığı tarafından ancak gerekmez çağrı sahibinin CRT kitaplığı tarafından ayrılan bir yığın içinde belirtilen bir işaretçi olduğunu doğrular. Visual Studio 2010 önce CRT sürümlerinde, bu belirtilen işaretçi yerel yığında (yalnızca hata ayıklama sürümü) olduğunu doğrular.

## <a name="syntax"></a>Sözdizimi

```C
int _CrtIsValidHeapPointer(
   const void *userData
);
```

### <a name="parameters"></a>Parametreler

*userData*<br/>
Ayrılan bellek bloğu başlangıcı için işaretçi.

## <a name="return-value"></a>Dönüş Değeri

**_Crtısvalidheappointer** yığınındaki tüm CRT kitaplığı örnekleri tarafından paylaşılan belirtilen işaretçi ise true değeri döndürür. Visual Studio 2010 önce CRT sürümlerinde, belirtilen işaretçi yerel yığında ise bu TRUE döndürür. Aksi takdirde işlev false değerini döndürür.

## <a name="remarks"></a>Açıklamalar

Bu işlevi kullanmak önerilmez. Visual Studio 2010 CRT kitaplığı ile başlayarak, bir işletim sistemi yığın tüm CRT kitaplığı paylaşan *işlem yığınını*. **_Crtısvalidheappointer** işlevi işaretçisi CRT yığınında, arayanın CRT kitaplığı tarafından ayrılmış olan ayrılmış ancak olup olmadığını bildirir. Örneğin, Visual Studio 2010 sürümünü CRT kitaplığını kullanarak ayrılmış bir blok göz önünde bulundurun. Varsa **_crtısvalidheappointer** CRT Kitaplığı Visual Studio 2012 sürümü tarafından dışarı aktarılan işlevin işaretçisi testleri, TRUE döndürür. Bu artık yararlı bir denemedir. CRT Kitaplığı Visual Studio 2010 önce sürümlerinde, işlev, belirli bir bellek adresi yerel yığın içinde olduğundan emin olmak için kullanılır. Yerel yığın oluşturulur ve C Çalışma Zamanı Kitaplığı'nın belirli bir örneği tarafından yönetilen yığın ifade eder. Bir dinamik bağlantı kitaplığı (DLL) çalışma zamanı kitaplığının statik bir bağlantı içeriyorsa, çalışma zamanı yığını ve bu nedenle, uygulamanın yerel yığın bağımsız kendi yığın kendi örneğini sahiptir. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar **_crtısvalidheappointer** ön işleme sırasında kaldırılır.

Bu işlev, TRUE veya false değeri döndürdüğünden, onu birine geçirilebilir [_ASSERT](assert-asserte-assert-expr-macros.md) makroları basit bir hata ayıklama hata işleme mekanizması oluşturmak için. Belirtilen adres yerel yığında yer değilse, aşağıdaki örnekte bir onaylama işlemi hatasına neden olur:

```C
_ASSERTE( _CrtIsValidHeapPointer( userData ) );
```

Hakkında daha fazla bilgi için **_crtısvalidheappointer** diğer hata ayıklama işlevlerini ve makrolarını birlikte kullanılabilir, bkz: [raporlama için makroları](/visualstudio/debugger/macros-for-reporting). Nasıl bellek blokları ayrılan, başlatılır ve taban yığının hata ayıklama sürümünde yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtIsValidHeapPointer**|\<crtdbg.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bellek, C çalışma zamanı kitaplıklarının önce Visual Studio 2010 ile kullanıldığında geçerli olup olmadığını test etmek nasıl gösterir. Bu örnekte, kullanıcılar eski CRT kitaplık kodu için sağlanır.

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
