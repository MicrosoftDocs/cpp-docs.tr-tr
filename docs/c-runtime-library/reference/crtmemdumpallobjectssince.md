---
title: _CrtMemDumpAllObjectsSince | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtMemDumpAllObjectsSince
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
- CrtMemDumpAllObjectsSince
- _CrtMemDumpAllObjectsSince
dev_langs:
- C++
helpviewer_keywords:
- _CrtMemDumpAllObjectsSince function
- CrtMemDumpAllObjectsSince function
ms.assetid: c48a447a-e6bb-475c-9271-a3021182a0dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 92d6148f6cbe49799a122d1745a6a6cde4c8be30
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44100385"
---
# <a name="crtmemdumpallobjectssince"></a>_CrtMemDumpAllObjectsSince

Program yürütme başlangıcından veya belirtilen yığın durumundan (yalnızca hata ayıklama sürümü) yığındaki nesneler hakkında bilgi dökümünü yapar.

## <a name="syntax"></a>Sözdizimi

```C
void _CrtMemDumpAllObjectsSince(
   const _CrtMemState *state
);
```

### <a name="parameters"></a>Parametreler

*durumu*<br/>
Gelen dökme başlamak için yığın durumuna yönelik işaretçi veya **NULL**.

## <a name="remarks"></a>Açıklamalar

**_CrtMemDumpAllObjectsSince** işlevi, hata ayıklama üst bilgi bilgileri kullanıcı tarafından okunabilen bir formda yığında ayrılan nesnelerin dökümünü alır. Döküm bilgilerini ayırmaları İzle ve bellek sorunlarını algılamak için uygulama tarafından kullanılabilir. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar **_CrtMemDumpAllObjectsSince** ön işleme sırasında kaldırılır.

**_CrtMemDumpAllObjectsSince** değerini kullanır *durumu* döküm işlemini başlatmak nereye belirlemek için parametre. Belirtilen yığın durumu dökme başlamak için *durumu* parametresi işaretçi olmalıdır bir **_CrtMemState** ile doldurulmuştur yapısı [_CrtMemCheckpoint](crtmemcheckpoint.md) önce **_CrtMemDumpAllObjectsSince** çağrıldı. Zaman *durumu* olduğu **NULL**, döküm program yürütme başlangıcından işlev başlar.

Uygulama bir döküm kanca işlevini çağırarak yüklü olmadığını [_CrtSetDumpClient](crtsetdumpclient.md), ardından her **_CrtMemDumpAllObjectsSince** hakkında bilgi dökümlerini bir **_clıent_block** türü bloğu, uygulama tarafından sağlanan döküm işlevi de çağırır. Varsayılan olarak, iç C çalışma zamanı blokları (**_CRT_BLOCK**) bellek dökümü işlemlerinde dahil edilmez. [_CrtSetDbgFlag](crtsetdbgflag.md) işlevi, açmak için kullanılabilir **_CRTDBG_CHECK_CRT_DF** , bit **_crtDbgFlag** bu blokları içerecek şekilde. Ayrıca, olarak işaretlenmiş blokların serbest veya göz ardı (**_FREE_BLOCK**, **_ıgnore_block**) bellek dökümü içinde yer almaz.

Yığın durumu işlevleri hakkında daha fazla bilgi ve **_CrtMemState** yapısı için bkz: [yığın durumu raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details). Nasıl bellek blokları ayrılan, başlatılır ve taban yığının hata ayıklama sürümünde yönetilen hakkında daha fazla bilgi için bkz. [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtMemDumpAll-ObjectsSince**|\<crtdbg.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="example"></a>Örnek

Nasıl kullanılacağını gösteren bir örnek **_CrtMemDumpAllObjectsSince**, bkz: [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2).

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
