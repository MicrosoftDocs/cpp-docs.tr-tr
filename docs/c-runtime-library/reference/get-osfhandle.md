---
title: _get_osfhandle
ms.date: 05/29/2018
api_name:
- _get_osfhandle
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
- get_osfhandle
- _get_osfhandle
helpviewer_keywords:
- operating systems, getting file handles
- get_osfhandle function
- _get_osfhandle function
- file handles [C++], operating system
ms.assetid: 0bdd728a-4fd8-410b-8c9f-01a121135196
ms.openlocfilehash: 65060689e0a7fc72b67da8fc3bf7ce0af75fd645
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70955778"
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

*FD* geçerliyse bir işletim sistemi dosya tutamacı döndürür. Aksi halde, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, **INVALID_HANDLE_VALUE** döndürür (-1). Ayrıca, geçersiz bir dosya tanıtıcısı belirten, **errno** 'U **EBADF**olarak ayarlar. Sonuç bir Win32 dosya tutamacı olarak kullanıldığında bir uyarı oluşmasını önlemek için bunu bir **tanıtıcı** türüne dönüştürün.

> [!NOTE]
> **STDIN**, **stdout**ve **stderr** bir Stream ile ilişkili değilse (örneğin, konsol penceresi olmayan bir Windows uygulamasında), bu akışlar için dosya tanımlayıcı değerleri özel değer olarak [_fileno](fileno.md) 'dan döndürülür. Benzer şekilde, bir **_fileno**çağrısının sonucu yerine dosya tanımlayıcısı parametresi olarak 0, 1 veya 2 kullanırsanız, **_get_osfhandle** Ayrıca dosya tanımlayıcısı bir akışa ilişkilendirilmediği zaman 2 özel değerini döndürür ve **errno**'u yapmaz. Ancak, bu geçerli bir dosya tanıtıcı değeri değildir ve bu işlemi kullanmaya çalışacak sonraki çağrılar başarısız olabilir.

**EBADF** ve diğer hata kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

İşletim sistemi (OS) dosya tanıtıcısı **_get_osfhandle**tarafından edinilen bir dosyayı kapatmak için, dosya tanımlayıcısı *FD*üzerinde [_close](close.md) öğesini çağırın. Bu işlevin dönüş değerindeki **CloseHandle** 'ı hiçbir şekilde çağırmayın. Temel alınan işletim sistemi dosya tanıtıcısı *FD* dosya tanımlayıcısına aittir ve *FD*üzerinde [_close](close.md) çağrıldığında kapalıdır. Dosya tanımlayıcısının bir `FILE *` akışa sahip olması durumunda, bu `FILE *` akışta [fclose](fclose-fcloseall.md) çağrısı hem dosya tanımlayıcısını hem de temel alınan işletim sistemi dosya tanıtıcısını kapatır. Bu durumda dosya tanımlayıcısında [_close](close.md) 'u çağırmayın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_osfhandle**|\<GÇ. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[\_open_osfhandle](open-osfhandle.md)
