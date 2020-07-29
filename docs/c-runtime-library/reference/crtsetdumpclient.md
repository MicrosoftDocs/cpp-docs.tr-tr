---
title: _CrtSetDumpClient
ms.date: 11/04/2016
api_name:
- _CrtSetDumpClient
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
- _CrtSetDumpClient
- CrtSetDumpClient
helpviewer_keywords:
- _CrtSetDumpClient function
- CrtSetDumpClient function
ms.assetid: f3dd06d0-c331-4a12-b68d-25378d112033
ms.openlocfilehash: fd2b037ce10f708ab133f31a20636438b0d04b93
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87234269"
---
# <a name="_crtsetdumpclient"></a>_CrtSetDumpClient

**_CLIENT_BLOCK** türü bellek bloklarının dökümünü almak için uygulama tanımlı bir işlev yüklüyor (yalnızca hata ayıklama sürümü).

## <a name="syntax"></a>Söz dizimi

```C
_CRT_DUMP_CLIENT _CrtSetDumpClient( _CRT_DUMP_CLIENT dumpClient );
```

### <a name="parameters"></a>Parametreler

*dumpClient*<br/>
C çalışma zamanı hata ayıklama belleği döküm işleminde kanca için yeni istemci tanımlı bellek dökümü işlevi.

## <a name="return-value"></a>Dönüş Değeri

Daha önce tanımlanan istemci blok dökümü işlevini döndürür.

## <a name="remarks"></a>Açıklamalar

**_CrtSetDumpClient** işlevi, uygulamanın, **_CLIENT_BLOCK** bellek bloklarında depolanan nesnelerin C çalışma zamanı hata ayıklama bellek dökümü sürecine dökümünü yapmak için kendi işlevini kullanmasına izin verir. Sonuç olarak, bir **_CLIENT_BLOCK** bellek bloğunu [_CrtMemDumpAllObjectsSince](crtmemdumpallobjectssince.md) veya [_CrtDumpMemoryLeaks](crtdumpmemoryleaks.md) gibi bir hata ayıklama dökümü işlevi her seferinde, uygulamanın döküm işlevi de çağrılır. **_CrtSetDumpClient** , bellek sızıntılarını algılamak ve **_CLIENT_BLOCK** bloklar halinde depolanan verilerin içeriğini doğrulamak için kolay bir yöntem sunan bir uygulama sağlar. [_DEBUG](../../c-runtime-library/debug.md) tanımlı olmadığında, **_CrtSetDumpClient** çağrıları ön işleme sırasında kaldırılır.

**_CrtSetDumpClient** Işlevi, *dumpistemcide* belirtilen yeni uygulama tanımlı döküm işlevini yüklüyor ve daha önce tanımlanmış döküm işlevini döndürüyor. İstemci bloğu döküm işlevine örnek olarak aşağıdaki gibidir:

```C
void DumpClientFunction( void *userPortion, size_t blockSize );
```

*Userbölüm* bağımsız değişkeni, bellek bloğunun Kullanıcı veri bölümünün başlangıcına yönelik bir Işaretçidir ve *blok boyutu* ayrılan bellek bloğunun boyutunu bayt cinsinden belirtir. İstemci blok dökümü işlevi döndürmelidir **`void`** . **_CrtSetDumpClient** geçirilen istemci dökümü işlevinin Işaretçisi, Crtdbg. h içinde tanımlanan **_CRT_DUMP_CLIENT**türüdür:

```C
typedef void (__cdecl *_CRT_DUMP_CLIENT)( void *, size_t );
```

**_CLIENT_BLOCK** türü bellek blokları üzerinde çalışan işlevler hakkında daha fazla bilgi için bkz. [Istemci blok kanca işlevleri](/visualstudio/debugger/client-block-hook-functions). [_CrtReportBlockType](crtreportblocktype.md) işlevi, blok türleri ve alt türleri hakkında bilgi döndürmek için kullanılabilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtSetDumpClient**|\<crtdbg.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

## <a name="see-also"></a>Ayrıca bkz.

[Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_CrtReportBlockType](crtreportblocktype.md)<br/>
[_CrtGetDumpClient](crtgetdumpclient.md)<br/>
