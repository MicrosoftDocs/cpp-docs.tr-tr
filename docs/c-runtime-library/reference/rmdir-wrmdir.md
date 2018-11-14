---
title: _rmdir, _wrmdir
ms.date: 11/04/2016
apiname:
- _wrmdir
- _rmdir
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- trmdir
- _trmdir
- wrmdir
- _rmdir
- _wrmdir
helpviewer_keywords:
- _rmdir function
- directories [C++], deleting
- rmdir function
- directories [C++], removing
- trmdir function
- _trmdir function
- _wrmdir function
- wrmdir function
ms.assetid: 652c2a5a-b0ac-4493-864e-1edf484333c5
ms.openlocfilehash: 0d0d9a25b70746174a66abbe088b297a5d9a0942
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51328012"
---
# <a name="rmdir-wrmdir"></a>_rmdir, _wrmdir

Bir dizini siler.

## <a name="syntax"></a>Sözdizimi

```C
int _rmdir(
   const char *dirname
);
int _wrmdir(
   const wchar_t *dirname
);
```

### <a name="parameters"></a>Parametreler

*DizinAdı*<br/>
Kaldırılacak dizinin yolu.

## <a name="return-value"></a>Dönüş Değeri

Dizin başarıyla silinirse bu işlevlerin her biri 0 döndürür. Hata-1 değeri belirtir ve **errno** aşağıdaki değerlerden birine ayarlayın:

|errno değeri|Koşul|
|-|-|
| **ENOTEMPTY** | Yol bir dizin değil, Dizin boş değil veya geçerli çalışma dizinine veya kök dizinine dizindir. |
| **ENOENT** | Yol geçersiz. |
| **SPAWN** | Bir programı dizini açık bir tanıtıcısı vardır. |

Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Rmdir** işlevi tarafından belirtilen dizin siler *DizinAdı*. Dizin boş olmalıdır ve geçerli çalışma dizinine veya kök dizinine olmamalıdır.

**_wrmdir** geniş karakterli sürümüdür **_rmdir**; *DizinAdı* bağımsız değişkeni **_wrmdir** geniş karakterli bir dizedir. **_wrmdir** ve **_rmdir** aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_trmdir**|**_rmdir**|**_rmdir**|**_wrmdir**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_rmdir**|\<Direct.h >|
|**_wrmdir**|\<Direct.h > veya \<wchar.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Örnek

Örneğin bakın [_mkdir](mkdir-wmkdir.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dizin Denetimi](../../c-runtime-library/directory-control.md)<br/>
[_chdir, _wchdir](chdir-wchdir.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
