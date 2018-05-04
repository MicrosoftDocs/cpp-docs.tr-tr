---
title: _get_osfhandle | Microsoft Docs
ms.custom: ''
ms.date: 12/12/2017
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _get_osfhandle
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
- get_osfhandle
- _get_osfhandle
dev_langs:
- C++
helpviewer_keywords:
- operating systems, getting file handles
- get_osfhandle function
- _get_osfhandle function
- file handles [C++], operating system
ms.assetid: 0bdd728a-4fd8-410b-8c9f-01a121135196
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8b58bbeb7c0b52950509dc8005551ad706577fcf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="getosfhandle"></a>_get_osfhandle

Belirtilen dosya tanımlayıcısı ile ilişkili işletim sistemi dosya işleci alır.

## <a name="syntax"></a>Sözdizimi

```C
intptr_t _get_osfhandle(
   int fd
);
```

### <a name="parameters"></a>Parametreler

*FD*<br/>
Varolan bir dosya tanımlayıcısı.

## <a name="return-value"></a>Dönüş Değeri

Bir işletim sistemi dosya işleci döndürür *fd* geçerlidir. Aksi takdirde, geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev, yürütme devam etmek için izin verilip verilmediğini, döndürür **INVALID_HANDLE_VALUE** (-1) ve ayarlar **errno** için **EBADF**, geçersiz bir dosya tanıtıcısı belirten.

## <a name="remarks"></a>Açıklamalar

İşletim sistemi (OS) dosya işleyici tarafından elde edilir bir dosyayı kapatmak için **_get_osfhandle**, çağrı [_close](close.md) dosya tanımlayıcısı üzerinde *fd*. Çağırmayın **CloseHandle** bu işlevin dönüş değeri. Temel işletim sistemi dosya işleci tarafından sahip olunan *fd* tanımlayıcısı dosya ve ne zaman kapalı [_close](close.md) üzerinde adlı *fd*. Dosya tanımlayıcısı aitse bir **dosya \***  stream, ardından çağırma [fclose](fclose-fcloseall.md) üzerindeki **dosya \***  akış dosya tanımlayıcısı kapatır ve temel işletim sistemi dosya işleci. Bu durumda, çağırmayın [_close](close.md) üzerinde dosya tanımlayıcısı.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_osfhandle**|\<io.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
