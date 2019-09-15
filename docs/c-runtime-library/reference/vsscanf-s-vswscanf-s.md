---
title: vsscanf_s, vswscanf_s
ms.date: 11/04/2016
api_name:
- vswscanf_s
- vsscanf_s
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
- vsscanf_s
- vswscanf_s
- _vstscanf_s
ms.assetid: 7b732e68-c6f4-4579-8917-122f5a7876e1
ms.openlocfilehash: bacda4288a6745ea57c31e68e515ae7b37418096
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70946028"
---
# <a name="vsscanf_s-vswscanf_s"></a>vsscanf_s, vswscanf_s

Bir dizeden biçimlendirilen verileri okur. [Vsscanf, vswscanf](vsscanf-vswscanf.md) 'in bu SÜRÜMLERINDE, [CRT 'daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleri vardır.

## <a name="syntax"></a>Sözdizimi

```C
int vsscanf_s(
   const char *buffer,
   const char *format,
   va_list argptr
);
int vswscanf_s(
   const wchar_t *buffer,
   const wchar_t *format,
   va_list arglist
);
```

### <a name="parameters"></a>Parametreler

*arabelleğin*<br/>
Depolanan veriler

*format*<br/>
Biçim denetimi dizesi. Daha fazla bilgi için bkz. [Biçim belirtimi alanları: scanf ve wscanf işlevleri](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).

*Arglist*<br/>
Değişken bağımsız değişken listesi.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, başarıyla dönüştürülen ve atanan alanların sayısını döndürür; dönüş değeri, okunan ancak atanmamış alanları içermez. 0 dönüş değeri hiçbir alan atanmadığını gösterir. Dönüş değeri bir hata **için veya** ilk dönüştürmeden önce dizenin sonuna ulaşılırsa.

*Arabellek* veya *Biçim* **null** işaretçisiyse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler-1 döndürür ve **errno** , **EINVAL**olarak ayarlanır.

Bu ve diğer hata kodları hakkında bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**Vsscanf_s** işlevi, *arabellekteki* verileri, *Arglist* bağımsız değişken listesindeki her bağımsız değişken tarafından verilen konumlara okur. Bağımsız değişken listesindeki bağımsız değişkenler, *biçimde*bir tür belirticisine karşılık gelen bir türe sahip değişkenlere işaretçiler belirtir. Daha az güvenli olan **vsscanf**sürümünden farklı olarak, **[]** içinde bulunan **c**, **c**, **s**, **s**veya String-Control kümelerini tür alan karakterlerini kullandığınızda bir arabellek boyutu parametresi gerekir. Karakter cinsinden arabellek boyutu, her bir arabellek parametresinden hemen sonra ek bir parametre olarak sağlanmalıdır.

Arabellek boyutu, Sonlandırıcı null değerini içerir. Bir genişlik belirtimi alanı, okunan belirtecin arabelleğe sığmasını sağlamak için kullanılabilir. Bir genişlik belirtimi alanı kullanılmıyorsa ve okunan belirteç arabelleğe sığmayacak kadar büyük ise, bu arabelleğe hiçbir şey yazılmaz.

Daha fazla bilgi için bkz. [scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md) ve [scanf Type alan karakterleri](../../c-runtime-library/scanf-type-field-characters.md).

> [!NOTE]
> Boyut parametresi, **size_t**değil, **işaretsiz**türündedir.

*Biçim* bağımsız değişkeni, giriş alanlarının yorumunu denetler ve **scanf_s** işlevi için *Biçim* bağımsız değişkeniyle aynı forma ve işleve sahiptir. Çakışan dizeler arasında kopyalama olursa davranış tanımsızdır.

**vswscanf_s** , **vsscanf_s**öğesinin geniş karakterli bir sürümüdür; **vswscanf_s** bağımsız değişkenleri geniş karakterli dizelerdir. **vsscanf_s** çok baytlı onaltılık karakterleri işlemez. **vswscanf_s** , Unicode tam genişlikli onaltılı veya "uyumluluk bölgesi" karakterlerini işlemez. Aksi halde, **vswscanf_s** ve **vsscanf_s** aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vstscanf_s**|**vsscanf_s**|**vsscanf_s**|**vswscanf_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**vsscanf_s**|\<stdio. h >|
|**vswscanf_s**|\<stdio. h > veya \<wchar. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_vsscanf_s.c
// compile with: /W3
// This program uses vsscanf_s to read data items
// from a string named tokenstring, then displays them.

#include <stdio.h>
#include <stdarg.h>
#include <stdlib.h>

int call_vsscanf_s(char *tokenstring, char *format, ...)
{
    int result;
    va_list arglist;
    va_start(arglist, format);
    result = vsscanf_s(tokenstring, format, arglist);
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
    call_vsscanf_s(tokenstring, "%80s", s, _countof(s));
    call_vsscanf_s(tokenstring, "%c", &c, sizeof(char));
    call_vsscanf_s(tokenstring, "%d", &i);
    call_vsscanf_s(tokenstring, "%f", &fp);

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

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l](sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[vsscanf, vswscanf](vsscanf-vswscanf.md)<br/>
