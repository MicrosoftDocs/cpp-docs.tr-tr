---
title: _pclose
ms.date: 4/2/2020
api_name:
- _pclose
- _o__pclose
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 6b35b8e3faa2f1a193dce102a6f8a11b9fcbb82b
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82910383"
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
Önceki **_popen**çağrısından değeri döndürün.

## <a name="return-value"></a>Dönüş Değeri

Sonlandırıcı komut işlemcisinin çıkış durumunu veya bir hata oluşursa-1 ' i döndürür. Dönüş değerinin biçimi, düşük sıralı ve yüksek sıralı baytlar yerine, **_cwait**ile aynıdır. Stream **null**ise, **_pclose** **errno** 'ı **EINVAL** olarak ayarlar ve-1 döndürür.

Bu ve diğer hata kodları hakkında bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Pclose** işlevi, ilişkili **_popen** çağrısı tarafından başlatılan komut işlemcisinin (cmd. exe) işlem kimliğini arar, yeni komut işlemcisinde bir [_cwait](cwait.md) çağrısı yürütür ve ilgili kanalda akışı kapatır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_pclose**|\<stdio. h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[_pipe](pipe.md)<br/>
[_popen, _wpopen](popen-wpopen.md)<br/>
