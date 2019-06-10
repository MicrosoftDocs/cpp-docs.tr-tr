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
ms.openlocfilehash: cc3b50e3d3f65bee83b8df83aa0adb5c8694e35a
ms.sourcegitcommit: 8adabe177d557c74566c13145196c11cef5d10d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/10/2019
ms.locfileid: "66821662"
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

Bir işletim sistemi dosya tanıtıcısı döndürür *fd* geçerlidir. Aksi takdirde, geçersiz parametre işleyicisi açıklandığı gibi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, döndürür **INVALID_HANDLE_VALUE** (-1). Ayrıca ayarlar **errno** için **EBADF**, geçersiz bir dosya işlemesi belirten. Bir uyarı sonucu bir Win32 dosya işleci kullanıldığında önlemek için yayınlayacağınızı bir **İŞLEMEK** türü.

> [!NOTE]
> Zaman **stdin**, **stdout**, ve **stderr** bulunmayan bir akış (örneğin, bir uygulamada Windows bir konsol penceresi olmadan), dosya tanımlayıcısı değerlerini ilişkili Bu akışları döndürülen [_fileno](fileno.md) -2 özel değer. Benzer şekilde, bir çağrı sonucunu yerine dosya tanımlayıcısı parametresi 0, 1 veya 2 kullanıyorsanız **_fileno**, **_get_osfhandle** ayrıca dosya tanımlayıcısı ilişkili olmadığında özel değeri -2 döndürür. bir akışı ve ayarlı değil **errno**. Ancak, bu geçerli bir dosya tanıtıcısı değeri değil ve bunu kullanma girişimi yapılan sonraki çağrılar büyük olasılıkla başarısız olur.

Hakkında daha fazla bilgi için **EBADF** ve diğer hata kodları [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Bir dosya olan işletim sistemi (OS) dosya tanıtıcısı ile elde edilir kapatmak için **_get_osfhandle**, çağrı [_close](close.md) dosya tanımlayıcısı üzerinde *fd*. Hiçbir çağrı **CloseHandle** bu işlevin dönüş değeri. Temel işletim sistemi dosya tanıtıcısı tarafından sahip olunan *fd* dosya tanımlayıcısı ve kapatılır [_close](close.md) üzerinde çağrılır *fd*. Dosya tanımlayıcısı aitse bir `FILE *` akış, ardından arama [fclose](fclose-fcloseall.md) üzerindeki `FILE *` hem dosya tanımlayıcısı hem de temel alınan işletim sistemi dosya tanıtıcısı akışı kapatır. Bu durumda, Remove() çağırmayın [_close](close.md) üzerinde dosya tanımlayıcısı.

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
[\_open_osfhandle](open-osfhandle.md)
