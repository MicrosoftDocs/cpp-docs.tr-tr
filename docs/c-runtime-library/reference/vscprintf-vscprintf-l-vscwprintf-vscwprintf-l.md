---
title: _vscprintf, _vscprintf_l, _vscwprintf, _vscwprintf_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _vscprintf
- _vscprintf_l
- _vscwprintf_l
- _vscwprintf
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
- vscprintf_l
- vscwpeintf
- _vscwprintf
- _vsctprintf
- _vscprintf
- vscwprintf_l
- vscprintf
- _vscwprintf_l
dev_langs:
- C++
helpviewer_keywords:
- vsctprintf function
- _vscprintf_l function
- _vsctprintf_l function
- _vsctprintf function
- _vscwprintf_l function
- vscwprintf_l function
- _vscprintf function
- _vscwprintf function
- vscwprintf function
- vsctprintf_l function
- formatted text [C++]
- vscprintf function
- vscprintf_l function
ms.assetid: 1bc67d3d-21d5-49c9-ac8d-69e26b16a3c3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c7b1771b065d7a0acc4db73eb188884086ff3b1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="vscprintf-vscprintfl-vscwprintf-vscwprintfl"></a>_vscprintf, _vscprintf_l, _vscwprintf, _vscwprintf_l

Bağımsız değişkenlerinin listesi için bir işaretçi kullanarak biçimlendirilmiş dizesindeki karakterlerin sayısını döndürür.

## <a name="syntax"></a>Sözdizimi

```C
int _vscprintf(
   const char *format,
   va_list argptr
);
int _vscprintf_l(
   const char *format,
   locale_t locale,
   va_list argptr
);
int _vscwprintf(
   const wchar_t *format,
   va_list argptr
);
int _vscwprintf_l(
   const wchar_t *format,
   locale_t locale,
   va_list argptr
);
```

### <a name="parameters"></a>Parametreler

*Biçimi*<br/>
Biçim denetimi dizesi.

*argptr*<br/>
İşaretçi bağımsız değişken listesi.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

Daha fazla bilgi için bkz: [biçim belirtimleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="return-value"></a>Dönüş Değeri

**_vscprintf** dize işaret varsa, bağımsız değişkenleri listesi tarafından oluşturulan karakter sayısını yazdırılması veya bir dosyaya gönderilen veya belirtilen biçimlendirme kullanarak arabellek kodlarını döndürür. Döndürülen değer sonlandırma null karakteri içermez. **_vscwprintf** geniş karakterler için aynı işlevi gerçekleştirir.

Bu işlevleri sürümlerini **_l** soneki, geçerli iş parçacığı yerel ayar yerine geçirilen yerel ayar parametresi kullanmasını dışında aynıdır.

Varsa *biçimi* null işaretçi açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, işlevleri -1 döndürür ve **errno** için **EINVAL**.

## <a name="remarks"></a>Açıklamalar

Her *bağımsız değişkeni* (varsa) karşılık gelen biçimi belirtiminde göre dönüştürülür *biçimi*. Biçim sıradan karakterden oluşan ve aynı form ve olarak işlev *biçimi* bağımsız değişkeni için [printf](printf-printf-l-wprintf-wprintf-l.md).

> [!IMPORTANT]
> Olması durumunda olun *biçimi* kullanıcı tanımlı bir dize sonlandırıldı null olduğundan ve doğru sayısı ve parametre türü vardır. Daha fazla bilgi için bkz: [önleme arabellek taşmasına neden](http://msdn.microsoft.com/library/windows/desktop/ms717795).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vsctprintf**|**_vscprintf**|**_vscprintf**|**_vscwprintf**|
|**_vsctprintf_l**|**_vscprintf_l**|**_vscprintf_l**|**_vscwprintf_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_vscprintf**, **_vscprintf_l**|\<stdio.h >|
|**_vscwprintf**, **_vscwprintf_l**|\<stdio.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bkz [vsprintf](vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md).

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[vprintf İşlevleri](../../c-runtime-library/vprintf-functions.md)<br/>
