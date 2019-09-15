---
title: _pclose
ms.date: 11/04/2016
api_name:
- _pclose
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
- api-ms-win-crt-stdio-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _pclose
- pclose
helpviewer_keywords:
- _pclose function
- pclose function
- pipes, closing
ms.assetid: e2e31a9e-ba3a-4124-bcbb-c4040110b3d3
ms.openlocfilehash: 383dd96553463a2619537cf06fc6534770ed88d5
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70951080"
---
# <a name="_pclose"></a>_pclose

Yeni bir komut işlemcisi bekler ve ilişkili kanalda akışı kapatır.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _pclose(
FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*ka*<br/>
Önceki çağrıdan **_popen**'a değer döndürür.

## <a name="return-value"></a>Dönüş Değeri

Sonlandırıcı komut işlemcisinin çıkış durumunu veya bir hata oluşursa-1 ' i döndürür. Dönüş değerinin biçimi, düşük sıralı ve yüksek sıralı baytlar yerine **getirildiğinden _cwait**ile aynıdır. Stream **null**ise, **_pclose** , **errno** ve **EINVAL** olarak ayarlar ve-1 döndürür.

Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Pclose** işlevi, ilişkili **_popen** çağrısı tarafından başlatılan komut işlemcisinin (cmd. exe) işlem kimliğini arar, yeni komut işlemcisinde bir [_cwait](cwait.md) çağrısı yürütür ve ilgili kanalda akışı kapatır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_pclose**|\<stdio. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[_pipe](pipe.md)<br/>
[_popen, _wpopen](popen-wpopen.md)<br/>
