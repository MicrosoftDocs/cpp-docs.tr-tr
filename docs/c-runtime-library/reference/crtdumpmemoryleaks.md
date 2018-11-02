---
title: _CrtDumpMemoryLeaks
ms.date: 11/04/2016
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
helpviewer_keywords:
- CrtDumpMemoryLeaks function
- CRTDBG_LEAK_CHECK_DF macro
- _CRTDBG_LEAK_CHECK_DF macro
- _CrtDumpMemoryLeaks function
- CRTDBG_CHECK_CRT_DF macro
- _CRTDBG_CHECK_CRT_DF macro
ms.assetid: 71b2eab4-7f55-44e8-a55a-bfea4f32d34c
ms.openlocfilehash: baf4f8d8234ba744acda20541d37bbc3ed076678
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531990"
---
# <a name="crtdumpmemoryleaks"></a>_CrtDumpMemoryLeaks

Bir bellek sızıntısı (yalnızca hata ayıklama sürümü) oluştuğunda dökümlerinde hata ayıklama yığınındaki tüm belleği engeller.

## <a name="syntax"></a>Sözdizimi

```C

int _CrtDumpMemoryLeaks( void );
```

## <a name="return-value"></a>Dönüş Değeri

**_CrtDumpMemoryLeaks** bir bellek sızıntısı bulunursa TRUE değerini döndürür. Aksi takdirde işlev false değerini döndürür.

## <a name="remarks"></a>Açıklamalar

**_CrtDumpMemoryLeaks** işlevi, program yürütme başlangıcından bir bellek sızıntısı oluşup oluşmadığını belirler. Sızıntı bulunduğunda, hata ayıklama üst bilgi bilgileri Yığındaki tüm nesneler için kullanıcı tarafından okunabilen bir biçimde dökümü yapıldığında. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar **_CrtDumpMemoryLeaks** ön işleme sırasında kaldırılır.

**_CrtDumpMemoryLeaks** sık sık uygulama tarafından ayrılan tüm belleği serbest bırakılmış doğrulamak için program yürütme sonunda çağrılır. İşlev otomatik olarak program sonlandırıldığında etkinleştirerek çağrılabilir **_CRTDBG_LEAK_CHECK_DF** bit alanı [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) kullanarak bayrak [_CrtSetDbgFlag](crtsetdbgflag.md)işlevi.

**_CrtDumpMemoryLeaks** çağrıları [_CrtMemCheckpoint](crtmemcheckpoint.md) yığın geçerli durumunu almak için ve ardından durum değil serbest bırakılmış bloklar tarar. Serbest bırakılmamış bir blok karşılaşıldığında **_CrtDumpMemoryLeaks** çağrıları [_CrtMemDumpAllObjectsSince](crtmemdumpallobjectssince.md) program yürütme başlangıcından yığında ayrılan tüm nesneler için döküm bilgiler.

Varsayılan olarak, iç C çalışma zamanı blokları (**_CRT_BLOCK**) bellek dökümü işlemlerinde dahil edilmez. [_CrtSetDbgFlag](crtsetdbgflag.md) işlevi, açmak için kullanılabilir **_CRTDBG_CHECK_CRT_DF** , bit **_crtDbgFlag** bu blokları sızıntı algılama işleminde içerecek şekilde.

Yığın durumu işlevleri hakkında daha fazla bilgi ve **_CrtMemState** yapısı için bkz: [yığın durumu raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details). Nasıl bellek blokları ayrılan, başlatılır ve taban yığının hata ayıklama sürümünde yönetilen hakkında daha fazla bilgi için bkz. [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtDumpMemoryLeaks**|\<crtdbg.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="example"></a>Örnek

Nasıl kullanılacağını gösteren bir örnek **_CrtDumpMemoryLeaks**, bkz: [crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1).

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
