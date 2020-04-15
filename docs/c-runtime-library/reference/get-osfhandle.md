---
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: a12c0c93ae15350a4b91a8aa905acb941f8b6a10
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345037"
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

*Fd*<br/>
Varolan bir dosya tanımlayıcısı.

## <a name="return-value"></a>Dönüş Değeri

*FD* geçerliyse işletim sistemi dosya tutamacı nı döndürür. Aksi takdirde, geçersiz parametre işleyicisi, [Parametre Doğrulama](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmenin devam etmesine izin verilirse, **INVALID_HANDLE_VALUE** (-1) döndürür. Ayrıca geçersiz bir dosya tutamacı gösteren **EBADF** **için errno** ayarlar. Sonuç Win32 dosya tutamacı olarak kullanıldığında bir uyarıyı önlemek için, bir **HANDLE** türüne döküm.

> [!NOTE]
> **Stdin,** **stdout**ve **stderr** bir akışla ilişkilendirilmediğinde (örneğin, konsol penceresi olmayan bir Windows uygulamasında), bu akışların dosya tanımlayıcı değerleri [_fileno](fileno.md) özel değer -2 olarak döndürülür. Benzer şekilde, **_fileno**için bir çağrı sonucu yerine dosya tanımlayıcı parametresi olarak 0, 1 veya 2 kullanıyorsanız, **_get_osfhandle** da dosya tanımlayıcısı bir akış ile ilişkili olmadığında özel değeri -2 döndürür ve **errno**ayarlamaz . Ancak, bu geçerli bir dosya işlemesi değeri değildir ve bunu kullanmaya çalışan sonraki çağrıların başarısız olma olasılığı yüksektir.

**EBADF** ve diğer hata kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)bakın.

## <a name="remarks"></a>Açıklamalar

İşletim sistemi (OS) dosya tutamacı **_get_osfhandle**tarafından elde edilen bir dosyayı kapatmak için, dosya *tanımlayıcıfd*üzerinde [_close](close.md) arayın. Bu işlevin geri dönüş değeri üzerinde **CloseHandle'ı** asla aramayın. Altta yatan işletim sistemi dosya tutamacı *fd* dosya tanımlayıcısı aittir ve [fd'de _close](close.md) çağrıldığında kapatılır. *fd* Dosya tanımlayıcısı bir `FILE *` akışa sahipse, bu `FILE *` akışta [fclose](fclose-fcloseall.md) araması hem dosya tanımlayıcısını hem de temel işletim sistemi dosya tanıtıcısını kapatır. Bu durumda, dosya tanımlayıcısı [üzerinde _close](close.md) aramayın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_osfhandle**|\<io.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Dosya Işleme](../../c-runtime-library/file-handling.md)<br/>
[_close](close.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[\_open_osfhandle](open-osfhandle.md)
