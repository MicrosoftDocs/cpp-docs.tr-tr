---
title: _CrtSetBreakAlloc
ms.date: 11/04/2016
api_name:
- _CrtSetBreakAlloc
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
- CrtSetBreakAlloc
- _CrtSetBreakAlloc
helpviewer_keywords:
- CrtSetBreakAlloc function
- _CrtSetBreakAlloc function
ms.assetid: 33bfc6af-a9ea-405b-a29f-1c2d4d9880a1
ms.openlocfilehash: e13c908c1efd1af9196885dee6e3b0f45845946b
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942309"
---
# <a name="_crtsetbreakalloc"></a>_CrtSetBreakAlloc

Belirtilen nesne ayırma sıra numarası (yalnızca hata ayıklama sürümü) üzerinde bir kesme noktası ayarlar.

## <a name="syntax"></a>Sözdizimi

```C
long _CrtSetBreakAlloc(
   long lBreakAlloc
);
```

### <a name="parameters"></a>Parametreler

*lBreakAlloc*<br/>
Kesme noktasının ayarlanacağı ayırma sıra numarası.

## <a name="return-value"></a>Dönüş Değeri

Bir kesme noktası ayarlanmış olan önceki nesne ayırma sıra numarasını döndürür.

## <a name="remarks"></a>Açıklamalar

**_Crtsetbreakkalloc** , bir uygulamanın belirli bir bellek ayırma noktasında ve isteğin kaynağına geri dönerek bellek sızıntısı algılaması gerçekleştirmesini sağlar. İşlevi, yığında ayrıldıktan sonra bellek bloğuna atanan sıralı nesne ayırma sıra numarasını kullanır. [_Hata ayıklama](../../c-runtime-library/debug.md) tanımlanmadığında, **_Crtsetbreakkalloc** çağrıları ön işleme sırasında kaldırılır.

Nesne ayırma sıra numarası, Crtdbg. h içinde tanımlanan **_CrtMemBlockHeader** yapısının *lRequest* alanında depolanır. Hata ayıklama döküm işlevlerinden biri tarafından bir bellek bloğu ile ilgili bilgi bildirildiğinde, bu sayı gibi {36}ayraç içine alınır.

**_Crtsetbreakkalloc** 'un diğer bellek yönetim işlevleriyle nasıl kullanılabileceği hakkında daha fazla bilgi için bkz. [yığın ayırma isteklerini izleme](/visualstudio/debugger/crt-debug-heap-details). Bellek bloklarının taban yığının hata ayıklama sürümünde nasıl ayrıldığı, başlatıldığı ve yönetildiği hakkında daha fazla bilgi için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtSetBreakAlloc**|\<Crtdbg. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

## <a name="example"></a>Örnek

```C
// crt_setbrkal.c
// compile with: -D_DEBUG /MTd -Od -Zi -W3 /c /link -verbose:lib -debug

/*
* In this program, a call is made to the _CrtSetBreakAlloc routine
* to verify that the debugger halts program execution when it reaches
* a specified allocation number.
*/

#include <malloc.h>
#include <crtdbg.h>

int main( )
{
        long allocReqNum;
        char *my_pointer;

        /*
         * Allocate "my_pointer" for the first
         * time and ensure that it gets allocated correctly
         */
        my_pointer = malloc(10);
        _CrtIsMemoryBlock(my_pointer, 10, &allocReqNum, NULL, NULL);

        /*
         * Set a breakpoint on the allocation request
         * number for "my_pointer"
         */
        _CrtSetBreakAlloc(allocReqNum+2);

        /*
         * Alternate freeing and reallocating "my_pointer"
         * to verify that the debugger halts program execution
         * when it reaches the allocation request
         */
        free(my_pointer);
        my_pointer = malloc(10);
        free(my_pointer);
        my_pointer = malloc(10);
        free(my_pointer);
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
