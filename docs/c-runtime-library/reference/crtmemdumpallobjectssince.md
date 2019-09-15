---
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
ms.openlocfilehash: 9e3793e9b88c593968b108e2801e24476417603c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942379"
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
Ya da **null**ile döküm başlatmaya başlamak için yığın durumunun işaretçisi.

## <a name="remarks"></a>Açıklamalar

**_CrtMemDumpAllObjectsSince** işlevi, yığında ayrılan nesnelerin hata ayıklama üstbilgi bilgilerini Kullanıcı tarafından okunabilen bir biçimde döker. Döküm bilgileri, uygulama tarafından ayırmaları izlemek ve bellek sorunlarını algılamak için kullanılabilir. [_Hata ayıklama](../../c-runtime-library/debug.md) tanımlanmadığında, **_CrtMemDumpAllObjectsSince** çağrıları ön işleme sırasında kaldırılır.

**_CrtMemDumpAllObjectsSince** , döküm işleminin nerede çalıştırılacağını belirlemekte kullanılacak *durum* parametresinin değerini kullanır. Belirtilen bir yığın durumundan dökme başlamak için *durum* parametresinin, **_CrtMemDumpAllObjectsSince** çağrılmadan önce [_CrtMemCheckpoint](crtmemcheckpoint.md) tarafından doldurulmuş bir **_CrtMemState** yapısına yönelik bir işaretçi olması gerekir. *Durum* **null**olduğunda, işlev program yürütme başlangıcından itibaren dökümü başlatır.

Uygulama, [_Crtsetdumpclient](crtsetdumpclient.md)' ı çağırarak bir döküm kancası işlevi yüklemiştir, **_CrtMemDumpAllObjectsSince** her seferinde bir **_client_block** türüyle ilgili bilgileri her zaman döker, uygulama tarafından sağlanan dökümü çağırır işlev de vardır. Varsayılan olarak, iç C çalışma zamanı blokları ( **_CRT_BLOCK**) bellek dökümü işlemlerine dahil edilmez. [_Crtsetdbgflag](crtsetdbgflag.md) işlevi, bu blokları dahil etmek Için **_Crtdbgflag** **_CRTDBG_CHECK_CRT_DF** bitini açmak üzere kullanılabilir. Ayrıca, serbest bırakılmış veya yoksayıldı ( **_Free_block**, **_IGNORE_BLOCK**) olarak işaretlenen bloklar bellek dökümünde yer alınmaz.

Yığın durumu işlevleri ve **_Crtmemstate** yapısı hakkında daha fazla bilgi için bkz. [yığın durum raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details). Bellek bloklarının taban yığının hata ayıklama sürümünde nasıl ayrıldığı, başlatıldığı ve yönetildiği hakkında daha fazla bilgi için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtMemDumpAll-ObjectsSince**|\<Crtdbg. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

## <a name="example"></a>Örnek

**_CrtMemDumpAllObjectsSince**'in nasıl kullanılacağına ilişkin bir örnek için bkz. [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2).

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
