---
title: _scprintf_p, _scprintf_p_l, _scwprintf_p, _scwprintf_p_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2120eaaee5acfa3628650b5df1f03448ee282a91
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="scprintfp-scprintfpl-scwprintfp-scwprintfpl"></a>_scprintf_p, _scprintf_p_l, _scwprintf_p, _scwprintf_p_l

Karakter sayısını biçimlendirilmiş dizisindeki parametreleri kullanılan biçim dizesi sırayı olanağı verir.

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

*Biçimi*<br/>
Biçim denetimi dizesi.

*Bağımsız değişken*<br/>
İsteğe bağlı bağımsız değişkenler.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Dize yazdırılması veya bir dosyayı veya belirtilen biçimlendirme kodlarını kullanarak arabellek gönderilen olsaydı, oluşturulacak karakterlerin sayısını döndürür. Döndürülen değer sonlandırma null karakteri içermez. **_scwprintf_p** geniş karakterler için aynı işlevi gerçekleştirir.

Arasındaki farkı **_scprintf_p** ve **_scprintf** olan **_scprintf_p** sırayı içinde belirtme verir destekler konumsal parametreler bağımsız değişkenler Biçim dizesi kullanılır. Daha fazla bilgi için bkz: [printf_p konumsal parametreler](../../c-runtime-library/printf-p-positional-parameters.md).

Varsa *biçimi* olan bir **NULL** işaretçi, geçersiz parametre işleyicisi çağrılır, açıklandığı gibi [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler -1 döndürür ve **errno** için **EINVAL**.

Bunlar ve diğer hata kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Her *bağımsız değişkeni* (varsa) karşılık gelen biçimi belirtiminde göre dönüştürülür *biçimi*. Biçim sıradan karakterden oluşan ve aynı form ve olarak işlev *biçimi* bağımsız değişkeni için [printf](printf-printf-l-wprintf-wprintf-l.md).

Bu işlevleri sürümlerini **_l** soneki, geçerli iş parçacığı yerel ayar yerine geçirilen yerel ayar parametresi kullanmasını dışında aynıdır.

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

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[_scprintf, _scprintf_l, _scwprintf, _scwprintf_l](scprintf-scprintf-l-scwprintf-scwprintf-l.md)<br/>
[_printf_p, _printf_p_l, _wprintf_p, _wprintf_p_l](printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)<br/>
