---
description: 'Hakkında daha fazla bilgi edinin: _CrtMemDumpAllObjectsSince'
title: _CrtMemDumpAllObjectsSince
ms.date: 11/04/2016
api_name:
- _CrtMemDumpAllObjectsSince
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
- CrtMemDumpAllObjectsSince
- _CrtMemDumpAllObjectsSince
helpviewer_keywords:
- _CrtMemDumpAllObjectsSince function
- CrtMemDumpAllObjectsSince function
ms.assetid: c48a447a-e6bb-475c-9271-a3021182a0dc
ms.openlocfilehash: e833543d3119b39a21b596af412a97f6991e4ef0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319644"
---
# <a name="_crtmemdumpallobjectssince"></a>_CrtMemDumpAllObjectsSince

Yığın içindeki nesneler hakkındaki bilgileri program yürütmenin başından veya belirtilen bir yığın durumundan (yalnızca hata ayıklama sürümü) döker.

## <a name="syntax"></a>Sözdizimi

```C
void _CrtMemDumpAllObjectsSince(
   const _CrtMemState *state
);
```

### <a name="parameters"></a>Parametreler

*durumunda*<br/>
Ya da **null** ile döküm başlatmaya başlamak için yığın durumunun işaretçisi.

## <a name="remarks"></a>Açıklamalar

**_CrtMemDumpAllObjectsSince** işlevi, Kullanıcı tarafından okunabilen bir formda yığında ayrılan nesnelerin hata ayıklama üstbilgi bilgilerini döker. Döküm bilgileri, uygulama tarafından ayırmaları izlemek ve bellek sorunlarını algılamak için kullanılabilir. [_DEBUG](../../c-runtime-library/debug.md) tanımlı olmadığında, **_CrtMemDumpAllObjectsSince** çağrıları ön işleme sırasında kaldırılır.

**_CrtMemDumpAllObjectsSince** , döküm işleminin nerede çalıştırılacağını belirlemekte kullanılacak *durum* parametresinin değerini kullanır. Belirtilen bir yığın durumundan dökme başlamak için, *durum* parametresinin **_CrtMemDumpAllObjectsSince** çağrılmadan önce [_CrtMemCheckpoint](crtmemcheckpoint.md) tarafından doldurulmuş **_CrtMemState** yapısına yönelik bir işaretçi olması gerekir. *Durum* **null** olduğunda, işlev program yürütme başlangıcından itibaren dökümü başlatır.

Uygulama, [_CrtSetDumpClient](crtsetdumpclient.md)çağırarak bir döküm kancası işlevi yüklemiştir, **_CrtMemDumpAllObjectsSince** her bir blok türü hakkında bilgi her **_CLIENT_BLOCK** her seferinde uygulama tarafından sağlanan döküm işlevini de çağırır. Varsayılan olarak, iç C çalışma zamanı blokları (**_CRT_BLOCK**) bellek dökümü işlemlerine dahil edilmez. [_CrtSetDbgFlag](crtsetdbgflag.md) işlevi, bu blokları dahil etmek için **_crtDbgFlag** **_CRTDBG_CHECK_CRT_DF** bitini açmak üzere kullanılabilir. Ayrıca, serbest bırakılmış veya yoksayıldı olarak işaretlenen bloklar (**_free_block**, **_IGNORE_BLOCK**) bellek dökümünde yer alınmaz.

Yığın durumu işlevleri ve **_CrtMemState** yapısı hakkında daha fazla bilgi için bkz. [yığın durumu raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details). Bellek bloklarının taban yığının hata ayıklama sürümünde nasıl ayrıldığı, başlatıldığı ve yönetildiği hakkında daha fazla bilgi için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtMemDumpAll-ObjectsSince**|\<crtdbg.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

## <a name="example"></a>Örnek

**_CrtMemDumpAllObjectsSince** kullanmanın bir örneği için bkz. [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2).

## <a name="see-also"></a>Ayrıca bkz.

[Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
