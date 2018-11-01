---
title: _scprintf_p, _scprintf_p_l, _scwprintf_p, _scwprintf_p_l
ms.date: 11/04/2016
apiname:
- _scwprintf_p
- _scprintf_p_l
- _scwprintf_p_l
- _scprintf_p
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
apitype: DLLExport
f1_keywords:
- _scwprintf_p_l
- _sctprintf_p
- scprintf_p_l
- scprintf_p
- _sctprintf_p_l
- scwprintf_p
- _scprintf_p_l
- scwprintf_p_l
- _scprintf_p
- _scwprintf_p
helpviewer_keywords:
- sctprintf_p_l function
- _scwprintf_p_l function
- scprintf_p_l function
- _scprintf_p function
- _scprintf_p_l function
- scprintf_p function
- sctprintf_p function
- _scwprintf_p function
- _sctprintf_p function
- scwprintf_p function
- scwprintf_p_l function
- _sctprintf_p_l function
ms.assetid: 8390d1e1-2826-47a4-851f-6635a88087cc
ms.openlocfilehash: 818dc5c24cca178fa03d08d1f609c23abbc7a013
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50443075"
---
# <a name="scprintfp-scprintfpl-scwprintfp-scwprintfpl"></a>_scprintf_p, _scprintf_p_l, _scwprintf_p, _scwprintf_p_l

Biçim dizesindeki parametreleri kullanılan sırayı belirtme olanağı ile bir biçimlendirilmiş dize ile karakter sayısını döndürür.

## <a name="syntax"></a>Sözdizimi

```C
int _scprintf_p(
   const char *format [,
   argument] ...
);
int _scprintf_p_l(
   const char *format,
   locale_t locale [,
   argument] ...
);
int _scwprintf_p (
   const wchar_t *format [,
   argument] ...
);
int _scwprintf_p _l(
   const wchar_t *format,
   locale_t locale [,
   argument] ...
);
```

### <a name="parameters"></a>Parametreler

*Biçim*<br/>
Biçim denetimi dizesi.

*Bağımsız değişken*<br/>
İsteğe bağlı bağımsız değişkenler.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Dize yazdırılması veya bir dosya veya belirtilen biçimlendirme kodları kullanılarak arabellek gönderilen çıkacaksa oluşturulacak karakter sayısını döndürür. Sondaki null karakter, döndürülen değer içermez. **_scwprintf_p** geniş karakterler için de aynı işlevi gerçekleştirir.

Arasındaki fark **_scprintf_p** ve **_scprintf** olan **_scprintf_p** içinde sırasını belirtmeye izin veren konum parametrelerini desteklemesidir bağımsız değişkenler Biçim dizesindeki kullanılır. Daha fazla bilgi için [printf_p konumsal parametreler](../../c-runtime-library/printf-p-positional-parameters.md).

Varsa *biçimi* olduğu bir **NULL** işaretçiyse, geçersiz parametre işleyicisi çağrılır, açıklandığı [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevler -1 döndürür ve **errno** için **EINVAL**.

Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Her *bağımsız değişken* (varsa) karşılık gelen kapsamındaki biçim belirtimine göre dönüştürülür *biçimi*. Biçim sıradan karakterlerden oluşur ve aynı forma ve işleve sahiptir *biçimi* için bağımsız değişken [printf](printf-printf-l-wprintf-wprintf-l.md).

Sahip bu işlevlerin sürümleri **_l** sonekine, geçerli iş parçacığı yerel ayarı yerine iletilen yerel ayar parametresini kullanmalarıdır.

> [!IMPORTANT]
> Emin *biçimi* kullanıcı tanımlı bir dize değil.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_sctprintf_p**|**_scprintf_p**|**_scprintf_p**|**_scwprintf_p**|
|**_sctprintf_p_l**|**_scprintf_p_l**|**_scprintf_p_l**|**_scwprintf_p_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_scprintf_p**, **_scprintf_p_l**|\<stdio.h >|
|**_scwprintf_p**, **_scwprintf_p_l**|\<stdio.h > veya \<wchar.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[_scprintf, _scprintf_l, _scwprintf, _scwprintf_l](scprintf-scprintf-l-scwprintf-scwprintf-l.md)<br/>
[_printf_p, _printf_p_l, _wprintf_p, _wprintf_p_l](printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)<br/>
