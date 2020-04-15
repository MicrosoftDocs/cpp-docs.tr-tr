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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: c66a749d6aeb74fdc677b2d6088e1b5093f3570b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338520"
---
# <a name="_pclose"></a>_pclose

Yeni bir komut işlemcisi bekler ve ilişkili boru üzerindeki akışı kapatır.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
int _pclose(
FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*Akışı*<br/>
Önceki çağrıdan **_popen'a**iade değeri.

## <a name="return-value"></a>Dönüş Değeri

Sonlandırıcı komut işlemcisinin çıkış durumunu veya bir hata oluşursa -1'i verir. İade değerinin biçimi, düşük sıralı ve yüksek sıralı baytların değiştirilmesi **dışında, _cwait**için de aynıdır. Akış **NULL**ise, **_pclose** **EINVAL** **için errno** ayarlar ve -1 döndürür.

Bu ve diğer hata kodları hakkında bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)bakın.

## <a name="remarks"></a>Açıklamalar

**_pclose** işlevi, ilişkili **_popen** çağrısı tarafından başlatılan komut işlemcisinin (Cmd.exe) işlem kimliğini arar, yeni komut işlemcisi üzerinde [_cwait](cwait.md) bir çağrı yürütür ve ilişkili boruüzerindeki akışı kapatır.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_pclose**|\<stdio.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="libraries"></a>Kitaplıklar

C çalışma [zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[_pipe](pipe.md)<br/>
[_popen, _wpopen](popen-wpopen.md)<br/>
