---
title: _CrtSetBreakAlloc | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _CrtSetBreakAlloc
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
- CrtSetBreakAlloc
- _CrtSetBreakAlloc
dev_langs:
- C++
helpviewer_keywords:
- CrtSetBreakAlloc function
- _CrtSetBreakAlloc function
ms.assetid: 33bfc6af-a9ea-405b-a29f-1c2d4d9880a1
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e14e1d40d5d20b9759d115eaf2fd29b3cae57172
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="crtsetbreakalloc"></a>_CrtSetBreakAlloc

Belirtilen nesnenin ayırma sipariş numarası (yalnızca hata ayıklama sürümü) üzerinde bir kesme noktası ayarlar.

## <a name="syntax"></a>Sözdizimi

```C
long _CrtSetBreakAlloc(
   long lBreakAlloc
);
```

### <a name="parameters"></a>Parametreler

*lBreakAlloc*<br/>
Kesme noktası ayarlanacak ayırma sipariş numarası.

## <a name="return-value"></a>Dönüş Değeri

Bir kesme vardı önceki nesne ayırma sıra numarasını döndürür.

## <a name="remarks"></a>Açıklamalar

**_CrtSetBreakAlloc** sonu bellek ayırma, belirli bir noktada ve isteğin başlangıç noktasının geri izleme tarafından bellek sızıntısı algılama gerçekleştirmek bir uygulama sağlar. İşlev yığınında ayrılmış olan bellek bloğu atanan sıralı nesne ayırma sipariş numarası kullanır. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar **_CrtSetBreakAlloc** ön işleme sırasında kaldırılır.

Nesne ayırma sipariş numarası depolanan *lRequest* alanını **_CrtMemBlockHeader** Crtdbg.h içinde tanımlanan yapısı. Bir bellek bloğu hakkında bilgi hata ayıklama dökümü işlevleri biri tarafından bildirildiğinde, bu sayı {36} gibi köşeli parantez içine alınır.

Hakkında daha fazla bilgi için **_CrtSetBreakAlloc** diğer bellek yönetimi işlevleri ile kullanılabilmesi için bkz: [yığın ayırma isteklerini izleme](/visualstudio/debugger/crt-debug-heap-details). Nasıl bellek blokları ayrılmış, başlatılmış ve temel yığın hata ayıklama sürümü yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtSetBreakAlloc**|\<crtdbg.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

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
