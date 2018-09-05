---
title: _getdcwd, _wgetdcwd | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _getdcwd
- _wgetdcwd
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
- wgetdcwd
- getdcwd
- _getdcwd
- tgetdcwd
- _wgetdcwd
- _tgetdcwd
dev_langs:
- C++
helpviewer_keywords:
- wgetdcwd function
- working directory
- getdcwd function
- _getdcwd function
- _wgetdcwd function
- current working directory
- directories [C++], current working
ms.assetid: 184152f5-c7b0-495b-918d-f9a6adc178bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 45c03ed2c057781c082988ac15e838249db0f28a
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43689721"
---
# <a name="getdcwd-wgetdcwd"></a>_getdcwd, _wgetdcwd

Belirtilen sürücüdeki geçerli çalışma dizininin tam yolunu alır.

## <a name="syntax"></a>Sözdizimi

```C
char *_getdcwd(
   int drive,
   char *buffer,
   int maxlen
);
wchar_t *_wgetdcwd(
   int drive,
   wchar_t *buffer,
   int maxlen
);
```

### <a name="parameters"></a>Parametreler

*Sürücü*<br/>
Sürücüyü belirten negatif olmayan tamsayı (0 = varsayılan sürücü, 1 = A, 2 = B vb.).

Belirtilen sürücü kullanılamıyorsa veya sürücü türünü (örneğin, çıkarılabilir, sabit, CD-ROM, RAM disk veya ağ sürücüsü) saptanamıyorsa, açıklanan geçersiz parametre işleyicisi [Parameter Validation](../../c-runtime-library/parameter-validation.md), olan çağrılır.

*Arabellek*<br/>
Yol için depolama konumu veya **NULL**.

Varsa **NULL** belirtilirse, bu işlev bir arabellek en az ayırır *maxlen* kullanarak boyut **malloc**, dönüş değeri **_getdcwd**ayrılan arabelleğin işaretçisidir. Arabellek çağrılarak serbest bırakılabileceğini **ücretsiz** ve çağrılıp işaretçi işleve.

*maxlen*<br/>
Karakter yolun maksimum uzunluğunu belirten sıfır olmayan pozitif bir tamsayı: **char** için **_getdcwd** ve **wchar_t** için **_wgetdcwd**.

Varsa *maxlen* açıklanan geçersiz parametre işleyicisi sıfırdan büyük değilse [Parameter Validation](../../c-runtime-library/parameter-validation.md), çağrılır.

## <a name="return-value"></a>Dönüş Değeri

Belirtilen sürücüdeki geçerli çalışma dizininin tam yolu temsil eden bir dize işaretçisi veya **NULL**, bir hata gösterir.

Varsa *arabellek* olarak belirtilen **NULL** ve ayırmak için yeterli bellek *maxlen* karakter, bir hata oluşur ve **errno** olduğu kümesine **ENOMEM**. Sondaki null karakter içeren yolun uzunluğu aşması durumunda *maxlen*, bir hata oluşur ve **errno** ayarlanır **ERANGE**. Bu hata kodları hakkında daha fazla bilgi için bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Getdcwd** işlevi belirtilen sürücüdeki geçerli çalışma dizininin tam yolunu alır ve depolar *arabellek*. Geçerli çalışma dizini kök olarak ayarlarsanız dize ters eğik çizgi ile sona erer (\\). Geçerli çalışma dizini kök dışında bir dizin olarak ayarlanırsa dize dizinin adı ve ters eğik çizgi ile değil sona erer.

**_wgetdcwd** geniş karakterli sürümüdür **_getdcwd**ve onun *arabellek* olan parametre ve dönüş değeri geniş karakterli dizelerdir. Aksi takdirde, **_wgetdcwd** ve **_getdcwd** aynı şekilde davranır.

Bağımlı olduğu halde bu işlev iş parçacığı açısından güvenli, **GetFullPathName**, kendisi iş parçacığı güvenli değildir. Ancak, çok iş parçacıklı uygulamanız hem bu işlevi çağırırsa iş parçacığı güvenliğini ihlal edebilirsiniz ve [GetFullPathNameA](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea).

Bu işlevin sürümünü **_nolock** soneki aynı şekilde davrandığını bu işlev için iş parçacığı açısından güvenli değildir ve başka iş parçacıklarının engellemelerinden korunmamaları. Daha fazla bilgi için [_getdcwd_nolock, _wgetdcwd_nolock](getdcwd-nolock-wgetdcwd-nolock.md).

Zaman **_DEBUG** ve **_CRTDBG_MAP_ALLOC** tanımlanır, çağrılar **_getdcwd** ve **_wgetdcwd** çağrılarıyladeğiştirilir **_getdcwd_dbg** ve **_wgetdcwd_dbg** böylece bellek ayırmalarını ayıklayabilirsiniz. Daha fazla bilgi için[_getdcwd_dbg, _wgetdcwd_dbg](getdcwd-dbg-wgetdcwd-dbg.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetdcwd**|**_getdcwd**|**_getdcwd**|**_wgetdcwd**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_getdcwd**|\<Direct.h >|
|**_wgetdcwd**|\<Direct.h > veya \<wchar.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örnekte bakın [_getdrive](getdrive.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dizin Denetimi](../../c-runtime-library/directory-control.md)<br/>
[_chdir, _wchdir](chdir-wchdir.md)<br/>
[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdrive](getdrive.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_rmdir, _wrmdir](rmdir-wrmdir.md)<br/>
