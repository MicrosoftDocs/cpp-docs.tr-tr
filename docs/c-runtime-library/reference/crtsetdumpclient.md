---
title: _CrtSetDumpClient | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtSetDumpClient
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
- _CrtSetDumpClient
- CrtSetDumpClient
dev_langs:
- C++
helpviewer_keywords:
- _CrtSetDumpClient function
- CrtSetDumpClient function
ms.assetid: f3dd06d0-c331-4a12-b68d-25378d112033
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8d5fecc90b4b7259f1440a0a0d86277c769c4e16
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32397229"
---
# <a name="crtsetdumpclient"></a>_CrtSetDumpClient

Dökümü uygulama tanımlı bir işlev yükler **_clıent_block** bellek blokları (yalnızca hata ayıklama sürümü) yazın.

## <a name="syntax"></a>Sözdizimi

```C
_CRT_DUMP_CLIENT _CrtSetDumpClient( _CRT_DUMP_CLIENT dumpClient );
```

### <a name="parameters"></a>Parametreler

*dumpClient*<br/>
C çalışma zamanı hata ayıklama bellek dökümü işlemine kanca yeni istemci tarafından tanımlanan bellek dökümü işlev.

## <a name="return-value"></a>Dönüş Değeri

Önceden tanımlanmış istemci bloğu döndüren dökümü işlevi.

## <a name="remarks"></a>Açıklamalar

**_CrtSetDumpClient** işlevi sağlayan kendi işlevi depolanan döküm nesnelere kanca uygulamaya **_clıent_block** bellek bloklara C çalışma zamanı hata ayıklama bellek dökümü işlemi. Sonuç olarak, her zaman bir hata ayıklama işlevi gibi dökümü [_CrtMemDumpAllObjectsSince](crtmemdumpallobjectssince.md) veya [_CrtDumpMemoryLeaks](crtdumpmemoryleaks.md) dökümleri bir **_clıent_block** bellek bloğu, uygulamanın Döküm işlevi de denir. **_CrtSetDumpClient** bir uygulama bellek sızıntılarını algılama ve doğrulama veya depolanan veri içeriğini Raporlama ile kolay bir yöntemini sağlar **_clıent_block** engeller. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar **_CrtSetDumpClient** ön işleme sırasında kaldırılır.

**_CrtSetDumpClient** işlevi yükler belirtilen yeni uygulama tanımlı döküm işlevi *dumpClient* ve önceden tanımlanmış döküm işlevi döndürür. İstemci blok döküm işlevi örneği aşağıdaki gibidir:

```C
void DumpClientFunction( void *userPortion, size_t blockSize );
```

*UserPortion* bağımsız değişkeni bir işaretçidir bellek bloğu kullanıcı veri bölümü başlangıcını ve *blok* blok boyutu ayrılan belleğin bayt cinsinden belirtir. İstemci blok döküm işlevi döndürmelidir **void**. Geçirilir istemci döküm işlev işaretçisi **_CrtSetDumpClient** türü **_crt_dump_clıent**, Crtdbg.h içinde tanımlanan:

```C
typedef void (__cdecl *_CRT_DUMP_CLIENT)( void *, size_t );
```

Üzerinde çalışan işlevler hakkında daha fazla bilgi için **_clıent_block** bellek blokları, bkz: [istemci blok kanca işlevleri](/visualstudio/debugger/client-block-hook-functions). [_CrtReportBlockType](crtreportblocktype.md) işlevi, blok türleri ve alt türleri hakkında bilgi döndürmek için kullanılabilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtSetDumpClient**|\<crtdbg.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_CrtReportBlockType](crtreportblocktype.md)<br/>
[_CrtGetDumpClient](crtgetdumpclient.md)<br/>
