---
title: _ungetc_nolock, _ungetwc_nolock
ms.date: 4/2/2020
api_name:
- _ungetwc_nolock
- _ungetc_nolock
- _o__ungetc_nolock
- _o__ungetwc_nolock
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
- _ungettc_nolock
- ungetwc_nolock
- ungetc_nolock
- _ungetc_nolock
- _ungetwc_nolock
helpviewer_keywords:
- _ungettc_nolock function
- _ungetwc_nolock function
- characters, pushing back onto stream
- _ungetc_nolock function
- ungetwc_nolock function
- ungettc_nolock function
- ungetc_nolock function
ms.assetid: aa02d5c2-1be1-46d2-a8c4-b61269e9d465
ms.openlocfilehash: fde5142d4c405fcf2dd61f642abe917d70b59b21
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361311"
---
# <a name="_ungetc_nolock-_ungetwc_nolock"></a>_ungetc_nolock, _ungetwc_nolock

Bir karakteri akışına geri iter.

## <a name="syntax"></a>Sözdizimi

```C
int _ungetc_nolock(
   int c,
   FILE *stream
);
wint_t _ungetwc_nolock(
   wint_t c,
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*C*<br/>
Karakter itilecek.

*Akışı*<br/>
**DOSYA** yapısı için işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, bu işlevlerin her biri karakter bağımsız *değişkeni c*döndürür. *C* geri itilen değilse veya karakter okunmamışsa, giriş akışı değişmez ve **_ungetc_nolock** **EOF**döndürür; **_ungetwc_nolock** **WEOF**döndürür. *Akış* **NULL**ise, **EOF** veya **WEOF** döndürülür ve **errno** **EINVAL**olarak ayarlanır.

Bu ve diğer hata kodları hakkında bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)bakın.

## <a name="remarks"></a>Açıklamalar

Bu işlevler **ungetc** ve **ungetwc**olmayan kilitleme sürümleridir. **_nolock** sonekli sürümler, diğer iş parçacıkları tarafından parazite karşı korunmayan sürümler dışında aynıdır. Diğer iş parçacığı kilitleme yükü ne sularına tabi olmadığından daha hızlı olabilir. Bu işlevleri yalnızca tek iş parçacığı uygulamaları gibi iş parçacığı güvenli bağlamlarda veya arama kapsamının iş parçacığı yalıtımını zaten işlediği durumlarda kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ungettc_nolock**|**_ungetc_nolock**|**_ungetc_nolock**|**_ungetwc_nolock**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_ungetc_nolock**|\<stdio.h>|
|**_ungetwc_nolock**|\<stdio.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
