---
title: _CrtMemDumpAllObjectsSince | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
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
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 30d502daad881417035a10b0a7ef3f4efcc41b4f
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="crtmemdumpallobjectssince"></a>_CrtMemDumpAllObjectsSince

Program yürütme başlangıç ya da belirtilen yığın durumu (yalnızca hata ayıklama sürümü) yığın nesneleri hakkında bilgi dökümünü yapar.

## <a name="syntax"></a>Sözdizimi

```C
void _CrtMemDumpAllObjectsSince(
   const _CrtMemState *state
);
```

### <a name="parameters"></a>Parametreler

*durumu* gelen dökme başlamak için yığın durumu işaretçisi veya **NULL**.

## <a name="remarks"></a>Açıklamalar

**_CrtMemDumpAllObjectsSince** işlevi, kullanıcı tarafından okunabilir bir biçimde yığınındaki ayrılmış nesnelerin hata ayıklama üst bilgileri dökümünü yapar. Döküm bilgilerini ayırmaları izlemek ve bellek sorunları algılamak için uygulama tarafından kullanılabilir. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar **_CrtMemDumpAllObjectsSince** ön işleme sırasında kaldırılır.

**_CrtMemDumpAllObjectsSince** değerini kullanır *durumu* döküm işlemi başlatmak nereye belirlemek için parametre. Belirtilen yığın durumundan dökme başlamaya *durumu* parametresi için bir işaretçi olmalıdır bir **_CrtMemState** tarafından doldurulmuştur yapısı [_CrtMemCheckpoint](crtmemcheckpoint.md) önce **_CrtMemDumpAllObjectsSince** çağrıldı. Zaman *durumu* olan **NULL**, program yürütme başından döküm işlevi başlar.

Uygulama bir döküm kanca işlevini çağırarak yüklü olmadığını [_CrtSetDumpClient](crtsetdumpclient.md), sonra her zaman **_CrtMemDumpAllObjectsSince** hakkında bilgi dökümleri bir **_clıent_block** türü bloğu, uygulama tarafından sağlanan döküm işlevi de çağırır. Varsayılan olarak, iç C çalışma zamanı blokları (**_CRT_BLOCK**) bellek dökümü işlemlerinde dahil edilmez. [_CrtSetDbgFlag](crtsetdbgflag.md) işlevi,'nı açmak için kullanılabilir **_CRTDBG_CHECK_CRT_DF** , bit **_crtDbgFlag** bu blokları içerecek şekilde. Ayrıca, olarak işaretlenmiş blokları serbest veya göz ardı (**_FREE_BLOCK**, **_ıgnore_block**) bellek dökümü dahil edilmez.

Yığın durumu İşlevler hakkında daha fazla bilgi ve **_CrtMemState** yapısı için bkz: [yığın durumu raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details). Nasıl bellek blokları ayrılmış, başlatılmış ve temel yığın hata ayıklama sürümü yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtMemDumpAll-ObjectsSince**|\<crtdbg.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="example"></a>Örnek

Nasıl kullanılacağına ilişkin bir örnek için **_CrtMemDumpAllObjectsSince**, bkz: [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2).

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
