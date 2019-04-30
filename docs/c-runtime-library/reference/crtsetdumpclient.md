---
title: _CrtSetDumpClient
ms.date: 11/04/2016
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
helpviewer_keywords:
- _CrtSetDumpClient function
- CrtSetDumpClient function
ms.assetid: f3dd06d0-c331-4a12-b68d-25378d112033
ms.openlocfilehash: 09f319f6298dbec6b229b2923bd86fc9b50314de
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64342990"
---
# <a name="crtsetdumpclient"></a>_CrtSetDumpClient

Dökümünü almak için uygulama tanımlı bir işlev yükler **_clıent_block** bellek blokları (yalnızca hata ayıklama sürümü).

## <a name="syntax"></a>Sözdizimi

```C
_CRT_DUMP_CLIENT _CrtSetDumpClient( _CRT_DUMP_CLIENT dumpClient );
```

### <a name="parameters"></a>Parametreler

*dumpClient*<br/>
C çalışma zamanı hata ayıklama bellek dökümü işlemine yeteneklerinizi yeni istemci tarafından tanımlanan bellek dökümü işlevi.

## <a name="return-value"></a>Dönüş Değeri

Önceden tanımlanmış istemci bloğu döndüren işlev dökümü.

## <a name="remarks"></a>Açıklamalar

**_CrtSetDumpClient** işlevine izin verir, uygulamanın kendi işlevine depolanan döküm nesnelere bağlama **_clıent_block** bellek bloklarda C çalışma zamanı hata ayıklama bellek dökümü işlem. Sonuç olarak, her seferinde bir hata ayıklama işlevi gibi dökümü [_CrtMemDumpAllObjectsSince](crtmemdumpallobjectssince.md) veya [_CrtDumpMemoryLeaks](crtdumpmemoryleaks.md) dökümleri bir **_clıent_block** bellek bloğu, uygulama Döküm işlev de çağrılır. **_CrtSetDumpClient** bir uygulama, bellek sızıntılarını algılama ve doğrulama veya depolanan verilerin içeriklerini Raporlama ile kolay bir yöntemini sağlar. **_clıent_block** engeller. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar **_CrtSetDumpClient** ön işleme sırasında kaldırılır.

**_CrtSetDumpClient** işlevi, belirtilen yeni uygulama tanımlı döküm işlevi yükler *dumpClient* ve önceden tanımlanmış döküm işlev döndürür. Bir istemci bloğu döküm işlev örneği aşağıdaki gibidir:

```C
void DumpClientFunction( void *userPortion, size_t blockSize );
```

*UserPortion* bağımsız kullanıcı veri bölümü bellek bloğunun başlangıcına bir işaretçidir ve *blockSize* blok boyutu ayrılan belleğin bayt cinsinden belirtir. İstemci bloğu döküm işlevi döndürmelidir **void**. Geçirilen istemci döküm işlev işaretçisi **_CrtSetDumpClient** türünde **_crt_dump_clıent**, Crtdbg.h tanımlandığı şekilde:

```C
typedef void (__cdecl *_CRT_DUMP_CLIENT)( void *, size_t );
```

Üzerinde çalışan işlevler hakkında daha fazla bilgi için **_clıent_block** bellek blokları, bkz: [istemci blok kanca işlevleri](/visualstudio/debugger/client-block-hook-functions). [_CrtReportBlockType](crtreportblocktype.md) işlevi, blok türleri ve alt türleri hakkında bilgi döndürmek için kullanılabilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtSetDumpClient**|\<crtdbg.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_CrtReportBlockType](crtreportblocktype.md)<br/>
[_CrtGetDumpClient](crtgetdumpclient.md)<br/>
