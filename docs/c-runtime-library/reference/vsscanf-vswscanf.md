---
description: 'Daha fazla bilgi edinin: vsscanf, vswscanf'
title: vsscanf, vswscanf
ms.date: 11/04/2016
api_name:
- vsscanf
- vswscanf
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _vstscanf
- vsscanf
- vswscanf
helpviewer_keywords:
- vswscanf function
- vsscanf function
ms.assetid: e96180f2-df46-423d-b4eb-0a49ab819bde
ms.openlocfilehash: 8659fc132c3b3c4f8fc36ef2f36122a53f1be6ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342094"
---
# <a name="vsscanf-vswscanf"></a>vsscanf, vswscanf

Bir dizeden biçimlendirilen verileri okur. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [vsscanf_s, vswscanf_s](vsscanf-s-vswscanf-s.md).

## <a name="syntax"></a>Sözdizimi

```C
int vsscanf(
   const char *buffer,
   const char *format,
   va_list arglist
);
int vswscanf(
   const wchar_t *buffer,
   const wchar_t *format,
   va_list arglist
);
```

### <a name="parameters"></a>Parametreler

*arabelleğin*<br/>
Depolanan veriler

*formatını*<br/>
Biçim denetimi dizesi. Daha fazla bilgi için bkz. [Biçim belirtimi alanları: scanf ve wscanf işlevleri](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).

*Arglist*<br/>
Değişken bağımsız değişken listesi.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, başarıyla dönüştürülen ve atanan alanların sayısını döndürür; dönüş değeri, okunan ancak atanmamış alanları içermez. 0 dönüş değeri hiçbir alan atanmadığını gösterir. Dönüş değeri bir hata **için veya** ilk dönüştürmeden önce dizenin sonuna ulaşılırsa.

*Arabellek* veya *Biçim* **null** işaretçisiyse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler-1 döndürür ve **errno** , **EINVAL** olarak ayarlanır.

Bu ve diğer hata kodları hakkında bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**Vsscanf** işlevi, *arabellekteki* verileri, *Arglist* bağımsız değişken listesindeki her bağımsız değişken tarafından verilen konumlara okur. Listedeki her bağımsız değişken, *biçimdeki* tür belirticisine karşılık gelen bir türe sahip bir değişkene işaretçi olmalıdır. *Biçim* bağımsız değişkeni, giriş alanlarının yorumunu denetler ve **scanf** işlevinin *Format* bağımsız değişkeniyle aynı forma ve işleve sahiptir. Çakışan dizeler arasında kopyalama gerçekleşmesi durumunda davranış tanımsızdır.

> [!IMPORTANT]
> Bir dizeyi okumak için **vsscanf** kullandığınızda, her zaman **% s** biçimi için bir genişlik belirleyin (örneğin, "% **s"** yerine **"% 32S"** ); Aksi halde, yanlış biçimlendirilmiş giriş arabellek taşmasına neden olabilir.

**vswscanf** , **vsscanf**; öğesinin geniş karakterli bir sürümüdür. **vswscanf** için bağımsız değişkenler geniş karakterli dizelerdir. **vsscanf** çok baytlı onaltılık karakterleri işlemez. **vswscanf** Unicode tam genişlikli onaltılı veya "uyumluluk bölgesi" karakterlerini işlemez. Aksi halde, **vswscanf** ve **vsscanf** aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vstscanf**|**vsscanf**|**vsscanf**|**vswscanf**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**vsscanf**|\<stdio.h>|
|**vswscanf**|\<stdio.h> veya \<wchar.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_vsscanf.c
// compile with: /W3
// This program uses vsscanf to read data items
// from a string named tokenstring, then displays them.

#include <stdio.h>
#include <stdarg.h>

int call_vsscanf(char *tokenstring, char *format, ...)
{
    int result;
    va_list arglist;
    va_start(arglist, format);
    result = vsscanf(tokenstring, format, arglist);
    va_end(arglist);
    return result;
}

int main( void )
{
    char  tokenstring[] = "15 12 14...";
    char  s[81];
    char  c;
    int   i;
    float fp;

    // Input various data from tokenstring:
    // max 80 character string:
    call_vsscanf(tokenstring, "%80s", s);
    call_vsscanf(tokenstring, "%c", &c);
    call_vsscanf(tokenstring, "%d", &i);
    call_vsscanf(tokenstring, "%f", &fp);

    // Output the data read
    printf("String    = %s\n", s);
    printf("Character = %c\n", c);
    printf("Integer:  = %d\n", i);
    printf("Real:     = %f\n", fp);
}
```

```Output
String    = 15
Character = 1
Integer:  = 15
Real:     = 15.000000
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış G/Ç](../../c-runtime-library/stream-i-o.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \_ _swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[vsscanf_s, vswscanf_s](vsscanf-s-vswscanf-s.md)<br/>
