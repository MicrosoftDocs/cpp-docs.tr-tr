---
title: vsscanf_s, vswscanf_s
ms.date: 11/04/2016
apiname:
- vswscanf_s
- vsscanf_s
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
- vsscanf_s
- vswscanf_s
- _vstscanf_s
ms.assetid: 7b732e68-c6f4-4579-8917-122f5a7876e1
ms.openlocfilehash: 3106e3533f5bb65334f8a4f3d38f55d886faef4c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50477174"
---
# <a name="vsscanfs-vswscanfs"></a>vsscanf_s, vswscanf_s

Biçimlendirilmiş verileri bir dizeden okur. Bu sürümleri [vsscanf, vswscanf](vsscanf-vswscanf.md) açıklandığı gibi güvenlik geliştirmeleri vardır [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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

*Arabellek*<br/>
Depolanan veri

*Biçim*<br/>
Biçim denetimi dizesi. Daha fazla bilgi için [biçim belirtimi alanları: scanf ve wscanf işlevleri](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).

*arglist*<br/>
Değişken bağımsız değişken listesi.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, başarıyla dönüştürülen ve atanan alanların sayısını döndürür; dönüş değeri, Okunmuş ancak atanmamış alanları içermez. 0 değeri hiçbir alan atanmamış belirtir. Dönüş değeri **EOF** bir hata için veya ilk dönüştürmeden önce dizenin sonuna ulaşılırsa.

Varsa *arabellek* veya *biçimi* olduğu bir **NULL** işaretçiyse, geçersiz parametre işleyicisi çağrılır, açıklandığı [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevler -1 döndürür ve **errno** için **EINVAL**.

Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**Vsscanf_s** işlevi, verileri okuyan *arabellek* her bağımsız değişkeni tarafından verilen konumlara *arglist* bağımsız değişken listesi. İçinde bir tür belirleyiciye karşılık gelen bir türe sahip değişkenler işaretçileri bağımsız değişken listesindeki bağımsız değişkenleri belirtmeniz *biçimi*. Daha az güvenli sürümünün aksine **vsscanf**, türü alan karakterleri kullandığınızda bir arabellek büyüklüğü parametresi gereklidir **c**, **C**, **s**, **S**, veya içine alınan dize denetim kümeleri **[]**. Karakter arabelleği boyutu, bunu gerektiren hemen her arabellek parametresinden sonra ek bir parametre olarak sağlanmalıdır.

Arabellek boyutu sondaki null karakterini içerir. Bir genişlik belirtimi alanı, okunan belirtecin arabelleğe sığmasını sağlamak için kullanılabilir. Hiçbir genişlik belirtimi alanı kullanılmazsa ve okunan belirteç arabelleğe sığamayacak kadar büyük ise, hiçbir şey o arabelleğe yazılır.

Daha fazla bilgi için [scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md) ve [scanf türü alan karakterleri](../../c-runtime-library/scanf-type-field-characters.md).

> [!NOTE]
> Boyut parametresi türünde **işaretsiz**değil **size_t**.

*Biçimi* giriş alanlarının yorumunu aynı bağımsız değişkeni denetler ve form ve işleve *biçimi* için bağımsız değişken **scanf_s** işlevi. Çakışan dizeler arasında kopyalama olursa davranış tanımsızdır.

**vswscanf_s** geniş karakterli sürümüdür **vsscanf_s**; bağımsız değişkenler **vswscanf_s** geniş karakterli dizelerdir. **vsscanf_s** çok baytlı onaltılı karakter işlemez. **vswscanf_s** tam genişlikli onaltılık Unicode veya "uyumluluk bölgesi" karakterlerini işlemez. Aksi takdirde, **vswscanf_s** ve **vsscanf_s** aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vstscanf_s**|**vsscanf_s**|**vsscanf_s**|**vswscanf_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**vsscanf_s**|\<stdio.h >|
|**vswscanf_s**|\<stdio.h > veya \<wchar.h >|

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

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l](sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[vsscanf, vswscanf](vsscanf-vswscanf.md)<br/>
