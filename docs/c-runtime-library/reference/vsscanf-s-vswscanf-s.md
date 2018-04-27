---
title: vsscanf_s, vswscanf_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
ms.assetid: 7b732e68-c6f4-4579-8917-122f5a7876e1
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 27f6a46b2a5a23b792775afcea0b84d11c220355
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="vsscanfs-vswscanfs"></a>vsscanf_s, vswscanf_s

Bir dizeden veri okuma biçimlendirilmiş. Bu sürümleri [vsscanf, vswscanf](vsscanf-vswscanf.md) açıklandığı gibi güvenlik geliştirmeleri sahip [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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
Depolanan verileri

*Biçimi*<br/>
Biçim denetimi dizesi. Daha fazla bilgi için bkz: [biçim belirtimi alanları: scanf ve wscanf işlevleri](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).

*arglist*<br/>
Değişken bağımsız değişken listesi.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri başarıyla dönüştürülür ve atanmış olan alan sayısını döndürür; dönüş değerini okumak ancak atanmamış alanları içermez. Dönüş değeri 0, hiçbir alan atandığını belirtir. Dönüş değeri **EOF** bir hata için veya dize sonu ilk dönüştürmeden önce ulaşılırsa.

Varsa *arabellek* veya *biçimi* olan bir **NULL** işaretçi, geçersiz parametre işleyicisi çağrılır, açıklandığı gibi [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler -1 döndürür ve **errno** için **EINVAL**.

Bunlar ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**Vsscanf_s** işlevi verileri okur *arabellek* her bağımsız değişkeni tarafından belirtilen konumları içine *arglist* bağımsız değişken listesi. Bağımsız değişken bağımsız değişken listesinde bir tür belirteci karşılık gelen bir türe sahip değişkenler işaretçiler belirtin *biçimi*. Daha az güvenli sürüm aksine **vsscanf**, türü alan karakterleri kullandığınızda bir arabellek boyutu parametresi gereklidir **c**, **C**, **s**, **S**, veya içinde içine dize denetim ayarlar **[]**. Arabellek boyutu karakter ek bir parametre bunu gerektiren hemen her arabellek parametre sonra sağlanmalıdır.

Arabellek boyutu sonlandırma null içerir. Genişlik belirtimi alanında okunduktan belirteci belleğe sığmayacak emin olmak için kullanılabilir. Genişlik belirtimi alan kullanılır ve okunan belirteci arabellek sığmayacak kadar büyük ise, hiçbir şey bu arabelleğe yazılır.

Daha fazla bilgi için bkz: [scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md) ve [scanf türü alan karakterleri](../../c-runtime-library/scanf-type-field-characters.md).

> [!NOTE]
> Boyutu parametresi türünde **imzasız**değil **size_t**.

*Biçimi* giriş yorumu alanları ve aynı bağımsız değişkeni denetimleri form ve olarak işlev *biçimi* bağımsız değişkeni için **scanf_s** işlevi. Çakışan dizeler arasında kopyalama olursa davranış tanımsızdır.

**vswscanf_s** bir joker karakter sürümü **vsscanf_s**; bağımsız değişkenleri **vswscanf_s** joker karakter dizelerdir. **vsscanf_s** onaltılık birden çok baytlı karakterler işlemez. **vswscanf_s** Unicode tam genişlikli onaltılık veya "uyumluluk bölge" karakterleri işlemez. Aksi takdirde, **vswscanf_s** ve **vsscanf_s** aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vstscanf_s**|**vsscanf_s**|**vsscanf_s**|**vswscanf_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**vsscanf_s**|\<stdio.h >|
|**vswscanf_s**|\<stdio.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
