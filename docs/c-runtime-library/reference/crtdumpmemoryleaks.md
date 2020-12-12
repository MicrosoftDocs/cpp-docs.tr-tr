---
description: 'Hakkında daha fazla bilgi edinin: _CrtDumpMemoryLeaks'
title: _CrtDumpMemoryLeaks
ms.date: 11/04/2016
api_name:
- _CrtDumpMemoryLeaks
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
- CRTDBG_LEAK_CHECK_DF
- CRTDBG_CHECK_CRT_DF
- _CRTDBG_LEAK_CHECK_DF
- CrtDumpMemoryLeaks
- _CrtDumpMemoryLeaks
- _CRTDBG_CHECK_CRT_DF
helpviewer_keywords:
- CrtDumpMemoryLeaks function
- CRTDBG_LEAK_CHECK_DF macro
- _CRTDBG_LEAK_CHECK_DF macro
- _CrtDumpMemoryLeaks function
- CRTDBG_CHECK_CRT_DF macro
- _CRTDBG_CHECK_CRT_DF macro
ms.assetid: 71b2eab4-7f55-44e8-a55a-bfea4f32d34c
ms.openlocfilehash: 83b3effdc4f3e8afdad24057ab55123aee924d60
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319784"
---
# <a name="_crtdumpmemoryleaks"></a>_CrtDumpMemoryLeaks

Bellek sızıntısı oluştuğunda hata ayıklama yığınındaki tüm bellek bloklarını döker (yalnızca hata ayıklama sürümü).

## <a name="syntax"></a>Syntax

```C

int _CrtDumpMemoryLeaks( void );
```

## <a name="return-value"></a>Dönüş Değeri

**_CrtDumpMemoryLeaks** , bellek sızıntısı bulunursa true değerini döndürür. Aksi takdirde, işlev FALSE döndürür.

## <a name="remarks"></a>Açıklamalar

**_CrtDumpMemoryLeaks** işlevi, program yürütme başlangıcından bu yana bir Bellek sızıntısının yapılıp yapılmayacağını belirler. Bir sızıntı bulunduğunda, yığındaki tüm nesneler için hata ayıklama üstbilgi bilgileri Kullanıcı tarafından okunabilen bir biçimde dökülür. [_DEBUG](../../c-runtime-library/debug.md) tanımlı olmadığında, **_CrtDumpMemoryLeaks** çağrıları ön işleme sırasında kaldırılır.

**_CrtDumpMemoryLeaks** , uygulama tarafından ayrılan tüm belleğin serbest bırakılmış olduğunu doğrulamak için genellikle program yürütmenin sonunda çağırılır. İşlevi, [_CrtSetDbgFlag](crtsetdbgflag.md) işlevi kullanılarak [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) bayrağının **_CRTDBG_LEAK_CHECK_DF** bit alanını etkinleştirerek program sonlandırmada otomatik olarak çağrılabilir.

**_CrtDumpMemoryLeaks** , yığının geçerli durumunu elde etmek için [_CrtMemCheckpoint](crtmemcheckpoint.md) çağırır ve sonra serbest bırakılmamış blokların durumunu tarar. Serbest bırakılmamış bir blok ile karşılaşıldığında **_CrtDumpMemoryLeaks** , program yürütme başlangıcından yığında ayrılan tüm nesneler için döküm bilgilerini [_CrtMemDumpAllObjectsSince](crtmemdumpallobjectssince.md) çağırır.

Varsayılan olarak, iç C çalışma zamanı blokları (**_CRT_BLOCK**) bellek dökümü işlemlerine dahil edilmez. [_CrtSetDbgFlag](crtsetdbgflag.md) işlevi, bu blokları sızıntı algılama işlemine dahil etmek için **_crtDbgFlag** **_CRTDBG_CHECK_CRT_DF** bitini açmak üzere kullanılabilir.

Yığın durumu işlevleri ve **_CrtMemState** yapısı hakkında daha fazla bilgi için bkz. [yığın durumu raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details). Bellek bloklarının taban yığının hata ayıklama sürümünde nasıl ayrıldığı, başlatıldığı ve yönetildiği hakkında daha fazla bilgi için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtDumpMemoryLeaks**|\<crtdbg.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

## <a name="example"></a>Örnek

**_CrtDumpMemoryLeaks** kullanmanın bir örneği için bkz. [crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1).

## <a name="see-also"></a>Ayrıca bkz.

[Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)<br/>
