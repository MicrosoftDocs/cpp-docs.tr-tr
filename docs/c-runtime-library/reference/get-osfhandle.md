---
title: _get_osfhandle
ms.date: 05/29/2018
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
helpviewer_keywords:
- operating systems, getting file handles
- get_osfhandle function
- _get_osfhandle function
- file handles [C++], operating system
ms.assetid: 0bdd728a-4fd8-410b-8c9f-01a121135196
ms.openlocfilehash: beab4e4308bc7bcde287366b78671f61a89f8827
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62332214"
---
# <a name="getosfhandle"></a>_get_osfhandle

Belirtilen dosya tanımlayıcı ile ilişkili olan işletim sistemi dosya tanıtıcısı alır.

## <a name="syntax"></a>Sözdizimi

```C
intptr_t _get_osfhandle(
   int fd
);
```

### <a name="parameters"></a>Parametreler

*FD*<br/>
Var olan bir dosya tanımlayıcısı.

## <a name="return-value"></a>Dönüş Değeri

Bir işletim sistemi dosya tanıtıcısı döndürür *fd* geçerlidir. Aksi takdirde, geçersiz parametre işleyicisi açıklandığı gibi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevi döndürür **INVALID_HANDLE_VALUE** (-1) ve ayarlar **errno** için **EBADF**, geçersiz bir dosya işlemesi belirten. Sonucu bir Win32 dosya işleci beklediğiniz çalışmalarında kullanıldığında, bir derleyici uyarısı önlemek için yayınlayacağınızı bir **İŞLEMEK** türü.

## <a name="remarks"></a>Açıklamalar

Bir dosya olan işletim sistemi (OS) dosya tanıtıcısı ile elde edilir kapatmak için **_get_osfhandle**, çağrı [_close](close.md) dosya tanımlayıcısı üzerinde *fd*. Çağırmayın **CloseHandle** bu işlevin dönüş değeri. Temel işletim sistemi dosya tanıtıcısı tarafından sahip olunan *fd* dosya tanımlayıcısı ve kapatılır [_close](close.md) üzerinde çağrılır *fd*. Dosya tanımlayıcısı aitse bir `FILE *` akış, ardından arama [fclose](fclose-fcloseall.md) üzerindeki `FILE *` hem dosya tanımlayıcısı hem de temel alınan işletim sistemi dosya tanıtıcısı akışı kapatır. Bu durumda, çağırmayın [_close](close.md) üzerinde dosya tanımlayıcısı.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_osfhandle**|\<io.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
