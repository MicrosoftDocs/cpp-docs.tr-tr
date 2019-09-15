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
ms.openlocfilehash: f739f86a8410c66135704d61944d122a38c196a5
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70938567"
---
# <a name="_crtsetdumpclient"></a>_CrtSetDumpClient

**_Client_block** türü bellek bloklarının dökümünü yapmak için uygulama tanımlı bir işlev yüklüyor (yalnızca hata ayıklama sürümü).

## <a name="syntax"></a>Sözdizimi

```C
_CRT_DUMP_CLIENT _CrtSetDumpClient( _CRT_DUMP_CLIENT dumpClient );
```

### <a name="parameters"></a>Parametreler

*dumpClient*<br/>
C çalışma zamanı hata ayıklama belleği döküm işleminde kanca için yeni istemci tanımlı bellek dökümü işlevi.

## <a name="return-value"></a>Dönüş Değeri

Daha önce tanımlanan istemci blok dökümü işlevini döndürür.

## <a name="remarks"></a>Açıklamalar

**_Crtsetdumpclient** işlevi, uygulamanın **_Client_block** bellek blokları içinde depolanan nesneleri C çalışma zamanı hata ayıklama bellek dökümü işlemine bağlamak için kendi işlevini kullanmasına izin verir. Sonuç olarak, [_CrtMemDumpAllObjectsSince](crtmemdumpallobjectssince.md) veya [_Crtdumpmemorysızıntı](crtdumpmemoryleaks.md) gibi bir hata ayıklama dökümü Işlevi **_client_block** bellek bloğunun dökümünü yapar, uygulamanın döküm işlevi de çağrılır. **_Crtsetdumpclient** , bellek sızıntılarını algılamaya ve **_Client_block** blokları 'nda depolanan verilerin içeriğini doğrulamaya veya raporlamaya yönelik kolay bir yöntem sunan bir uygulama sağlar. [_Hata ayıklama](../../c-runtime-library/debug.md) tanımlanmadığında, **_Crtsetdumpclient** çağrıları ön işleme sırasında kaldırılır.

**_Crtsetdumpclient** Işlevi, *dumpclient* 'da belirtilen yeni uygulama tanımlı döküm işlevini yüklüyor ve daha önce tanımlanmış döküm işlevini döndürüyor. İstemci bloğu döküm işlevine örnek olarak aşağıdaki gibidir:

```C
void DumpClientFunction( void *userPortion, size_t blockSize );
```

*Userbölüm* bağımsız değişkeni, bellek bloğunun Kullanıcı veri bölümünün başlangıcına yönelik bir Işaretçidir ve *blok boyutu* ayrılan bellek bloğunun boyutunu bayt cinsinden belirtir. İstemci blok dökümü işlevi **void**döndürmelidir. **_Crtsetdumpclient** öğesine geçirilen istemci dökümü işlevinin Işaretçisi, Crtdbg. h Içinde tanımlanan **_CRT_DUMP_CLIENT**türündedir:

```C
typedef void (__cdecl *_CRT_DUMP_CLIENT)( void *, size_t );
```

**_Client_block** türü bellek blokları üzerinde çalışan işlevler hakkında daha fazla bilgi için bkz. [Istemci blok kanca işlevleri](/visualstudio/debugger/client-block-hook-functions). [_Crtreportblocktype](crtreportblocktype.md) işlevi, blok türleri ve alt türleri hakkında bilgi döndürmek için kullanılabilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtSetDumpClient**|\<Crtdbg. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) sürümlerini ayıklayın.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_CrtReportBlockType](crtreportblocktype.md)<br/>
[_CrtGetDumpClient](crtgetdumpclient.md)<br/>
