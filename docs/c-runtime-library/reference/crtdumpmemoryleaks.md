---
title: _CrtDumpMemoryLeaks | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtDumpMemoryLeaks
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
- CRTDBG_LEAK_CHECK_DF
- CRTDBG_CHECK_CRT_DF
- _CRTDBG_LEAK_CHECK_DF
- CrtDumpMemoryLeaks
- _CrtDumpMemoryLeaks
- _CRTDBG_CHECK_CRT_DF
dev_langs:
- C++
helpviewer_keywords:
- CrtDumpMemoryLeaks function
- CRTDBG_LEAK_CHECK_DF macro
- _CRTDBG_LEAK_CHECK_DF macro
- _CrtDumpMemoryLeaks function
- CRTDBG_CHECK_CRT_DF macro
- _CRTDBG_CHECK_CRT_DF macro
ms.assetid: 71b2eab4-7f55-44e8-a55a-bfea4f32d34c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 68a187283eedadcd2f435b0900fde648a5010368
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="crtdumpmemoryleaks"></a>_CrtDumpMemoryLeaks

Bellek sızıntısı (yalnızca hata ayıklama sürümü) oluştuğunda dökümleri tüm bellek hata ayıklama yığınında engeller.

## <a name="syntax"></a>Sözdizimi

```C

int _CrtDumpMemoryLeaks( void );
```

## <a name="return-value"></a>Dönüş Değeri

**_CrtDumpMemoryLeaks** bellek sızıntısı bulunursa TRUE değerini döndürür. Aksi takdirde işlevi FALSE değerini döndürür.

## <a name="remarks"></a>Açıklamalar

**_CrtDumpMemoryLeaks** işlevi bellek sızıntısı program yürütme başladığından bu yana gerçekleşip gerçekleşmediğini belirler. Yığın içindeki tüm nesneler için hata ayıklama üst bilgileri, bir sızıntısı bulunduğunda, kullanıcı tarafından okunabilir bir biçimde edebilir. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar **_CrtDumpMemoryLeaks** ön işleme sırasında kaldırılır.

**_CrtDumpMemoryLeaks** sık sık uygulama tarafından ayrılan tüm belleği serbest olduğunu doğrulamak için program yürütme sonunda çağrılır. İşlev otomatik olarak program sonlandırmanın açarak çağrılabilir **_CRTDBG_LEAK_CHECK_DF** bit alanı [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) kullanarak bayrak [_CrtSetDbgFlag](crtsetdbgflag.md)işlevi.

**_CrtDumpMemoryLeaks** çağrıları [_CrtMemCheckpoint](crtmemcheckpoint.md) öbek geçerli durumunu almak için değil serbest blokları durumu tarar. Serbest bırakılmamış blok karşılaşıldığında, **_CrtDumpMemoryLeaks** çağrıları [_CrtMemDumpAllObjectsSince](crtmemdumpallobjectssince.md) program yürütme başlangıcı yığınından ayrılan tüm nesneleri için döküm bilgi.

Varsayılan olarak, iç C çalışma zamanı blokları (**_CRT_BLOCK**) bellek dökümü işlemlerinde dahil edilmez. [_CrtSetDbgFlag](crtsetdbgflag.md) işlevi,'nı açmak için kullanılabilir **_CRTDBG_CHECK_CRT_DF** , bit **_crtDbgFlag** sızıntısı algılama işleminde bu blokları içerecek şekilde.

Yığın durumu İşlevler hakkında daha fazla bilgi ve **_CrtMemState** yapısı için bkz: [yığın durumu raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details). Nasıl bellek blokları ayrılmış, başlatılmış ve temel yığın hata ayıklama sürümü yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtDumpMemoryLeaks**|\<crtdbg.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="example"></a>Örnek

Nasıl kullanılacağına ilişkin bir örnek için **_CrtDumpMemoryLeaks**, bkz: [crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1).

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
