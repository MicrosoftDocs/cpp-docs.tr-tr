---
description: 'Hakkında daha fazla bilgi edinin: _get_osfhandle'
title: _get_osfhandle
ms.date: 4/2/2020
api_name:
- _get_osfhandle
- _o__get_osfhandle
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
- get_osfhandle
- _get_osfhandle
helpviewer_keywords:
- operating systems, getting file handles
- get_osfhandle function
- _get_osfhandle function
- file handles [C++], operating system
ms.assetid: 0bdd728a-4fd8-410b-8c9f-01a121135196
ms.openlocfilehash: 72f6a2f695868bdc4a5d13c09d1d34152cf9e51e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321142"
---
# <a name="_get_osfhandle"></a>_get_osfhandle

Belirtilen dosya tanımlayıcısıyla ilişkili işletim sistemi dosya tanıtıcısını alır.

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

*FD* geçerliyse bir işletim sistemi dosya tutamacı döndürür. Aksi halde, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa **INVALID_HANDLE_VALUE** (-1) döndürür. Ayrıca, geçersiz bir dosya tanıtıcısı belirten, **errno** 'U **EBADF** olarak ayarlar. Sonuç bir Win32 dosya tutamacı olarak kullanıldığında bir uyarı oluşmasını önlemek için bunu bir **tanıtıcı** türüne dönüştürün.

> [!NOTE]
> **STDIN**, **stdout** ve **stderr** bir Stream ile ilişkili değilse (örneğin, konsol penceresi olmayan bir Windows uygulamasında), bu akışlar için dosya tanımlayıcı değerleri, 1 ' den özel değer olarak [_fileno](fileno.md) döndürülür. Benzer şekilde, bir **_fileno** çağrısının sonucu yerine dosya tanımlayıcısı parametresi olarak bir 0, 1 veya 2 kullanırsanız, **_get_osfhandle** Ayrıca, dosya tanımlayıcısı bir akışa ilişkilendirilmediği zaman 2 özel değerini döndürür ve **errno**'u yapmaz. Ancak, bu geçerli bir dosya tanıtıcı değeri değildir ve bu işlemi kullanmaya çalışacak sonraki çağrılar başarısız olabilir.

**EBADF** ve diğer hata kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

İşletim sistemi (OS) dosya tanıtıcısı **_get_osfhandle** tarafından alınan bir dosyayı kapatmak için, dosya tanımlayıcısı *FD* üzerinde [_close](close.md) çağırın. Bu işlevin dönüş değerindeki **CloseHandle** 'ı hiçbir şekilde çağırmayın. Temel alınan işletim sistemi dosya tanıtıcısı *FD* dosya tanımlayıcısına aittir ve [_close](close.md) *FD* üzerinde çağrıldığında kapalıdır. Dosya tanımlayıcısının bir akışa sahip olması durumunda `FILE *` , Bu akışta [fclose](fclose-fcloseall.md) çağrısı `FILE *` hem dosya tanımlayıcısını hem de temel alınan işletim sistemi dosya tanıtıcısını kapatır. Bu durumda, dosya tanımlayıcısında [_close](close.md) çağırmayın.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_osfhandle**|\<io.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[\_open_osfhandle](open-osfhandle.md)
