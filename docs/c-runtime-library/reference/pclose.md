---
title: _pclose
ms.date: 11/04/2016
apiname:
- _pclose
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _pclose
- pclose
helpviewer_keywords:
- _pclose function
- pclose function
- pipes, closing
ms.assetid: e2e31a9e-ba3a-4124-bcbb-c4040110b3d3
ms.openlocfilehash: eb0f54ec27992cd0e62b11d8fec5bd54c3daea4b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156020"
---
# <a name="pclose"></a>_pclose

Yeni bir komut işlemcisini bekler ve ilişkili kanalda akışı kapatır.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _pclose(
FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*Stream*<br/>
Önceki çağrıdan dönüş değeri **_popen**.

## <a name="return-value"></a>Dönüş Değeri

Bir hata oluşursa, -1 veya sonlanmakta olan komut işleyicisinin çıkış durumunu döndürür. Dönüş değerinin biçimi için aynıdır **_cwait**düşük düzey ve yüksek düzeyli formatın dışında. Akış ise **NULL**, **_pclose** ayarlar **errno** için **EINVAL** ve -1 döndürür.

Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Pclose** işlevi, ilişkili tarafından başlatılan komut işleyicisi (Cmd.exe) işlem Kimliğini şuna **_popen** çağrı, yürüten bir [_cwait](cwait.md) yeni komutunu çağırın İşlemci ve ilişkili kanalda akışı kapatır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_pclose**|\<stdio.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[_pipe](pipe.md)<br/>
[_popen, _wpopen](popen-wpopen.md)<br/>
