---
title: _cscanf_s, _cscanf_s_l, _cwscanf_s, _cwscanf_s_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _cwscanf_s_l
- _cwscanf_s
- _cscanf_s
- _cscanf_s_l
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
- cscanf_s
- cscanf_s_l
- cwscanf_s
- _cwscanf_s
- _tcscanf_s
- _cscanf_s
- _cwscanf_s_l
- _cscanf_s_l
- cwscanf_s_l
- _tcscanf_s_l
- tcscanf_s
- tcscanf_s_l
dev_langs:
- C++
helpviewer_keywords:
- cscanf_s function
- _cwscanf_s_l function
- tcscanf_s function
- console [C++], reading from
- _cscanf_s function
- data [C++], reading from the console
- cwscanf_s function
- _tcscanf_s_l function
- _cscanf_s_l function
- cscanf_s_l function
- cwscanf_s_l function
- reading data [C++], from the console
- _cwscanf_s function
- _tcscanf_s function
- tcscanf_s_l function
ms.assetid: 9ccab74d-916f-42a6-93d8-920525efdf4b
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e1f63ddf6655c9a8d283c8a1b1e6e99bd1a13869
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="cscanfs-cscanfsl-cwscanfs-cwscanfsl"></a>_cscanf_s, _cscanf_s_l, _cwscanf_s, _cwscanf_s_l

Okuma veri konsolundan biçimlendirilmiş. Bu daha güvenli sürümlerini [_cscanf, _cscanf_l, _cwscanf, _cwscanf_l](cscanf-cscanf-l-cwscanf-cwscanf-l.md) açıklandığı gibi güvenlik geliştirmeleri sahip [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _cscanf_s(
   const char *format [,
   argument] ...
);
int _cscanf_s_l(
   const char *format,
   locale_t locale [,
   argument] ...
);
int _cwscanf_s(
   const wchar_t *format [,
   argument] ...
);
int _cwscanf_s_l(
   const wchar_t *format,
   locale_t locale [,
   argument] ...
);
```

### <a name="parameters"></a>Parametreler

*Biçimi*<br/>
Biçim denetimi dizesi.

*Bağımsız değişken*<br/>
İsteğe bağlı parametreler.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Başarılı bir şekilde dönüştürülür ve atanan alan sayısı. Dönüş değerini okumak ancak atanmamış alanları içermez. Dönüş değeri **EOF** için son dosya okuma girişimi. Klavye girişi işletim sistemi komut satırı düzeyinde yönlendirildiğinde bu durum oluşabilir. Dönüş değeri hiçbir alan atanmış 0 anlamına gelir.

Bu işlevler kendi parametreleri doğrulayın. Varsa *biçimi* null işaretçi açıklandığı gibi bu işlevleri geçersiz parametre işleyicisi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütme devam etmek için izin verilip verilmediğini, bu işlevlerin dönüş **EOF** ve **errno** ayarlanır **EINVAL**.

## <a name="remarks"></a>Açıklamalar

**_Cscanf_s** işlevi tarafından verilen konumları içine doğrudan konsolundan veri okuyan *bağımsız değişkeni*. [_Getche](getch-getwch.md) işlevi karakterleri okumak için kullanılır. Her isteğe bağlı parametresi bir tür belirteci karşılık gelen türüne sahip bir değişken için bir işaretçi olmalıdır *biçimi*. Giriş yorumu alanları ve aynı biçim denetimleri form ve olarak işlev *biçimi* parametresi için [scanf_s](scanf-scanf-l-wscanf-wscanf-l.md) işlevi. Sırada **_cscanf_s** normalde giriş karakter görüntülemektedir son çağrı yapmak ise, bunu yapmaz **_ungetch**.

Gibi işlevlerde güvenli diğer sürümlerini **scanf** ailesi, **_cscanf_s** ve **_cswscanf_s** türü alan karakterleri boyutu bağımsız değişkenleri gerektiren **c** , **C**, **s**, **S**, ve **[**. Daha fazla bilgi için bkz: [sacnf genişlik belirtimi](../../c-runtime-library/scanf-width-specification.md).

> [!NOTE]
> Boyutu parametresi türünde **imzasız**değil **size_t**.

Bu işlevleri sürümlerini **_l** soneki, geçerli iş parçacığı yerel ayar yerine geçirilen yerel ayar parametresi kullanmasını dışında aynıdır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcscanf_s**|**_cscanf_s**|**_cscanf_s**|**_cwscanf_s**|
|**_tcscanf_s_l**|**_cscanf_s_l**|**_cscanf_s_l**|**_cwscanf_s_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_cscanf_s**, **_cscanf_s_l**|\<conio.h >|
|**_cwscanf_s**, **_cwscanf_s_l**|\<conio.h > veya \<wchar.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Örnek

```C
// crt_cscanf_s.c
// compile with: /c
/* This program prompts for a string
* and uses _cscanf_s to read in the response.
* Then _cscanf_s returns the number of items
* matched, and the program displays that number.
*/

#include <stdio.h>
#include <conio.h>

int main( void )
{
   int result, n[3];
   int i;

   result = _cscanf_s( "%i %i %i", &n[0], &n[1], &n[2] );
   _cprintf_s( "\r\nYou entered " );
   for( i=0; i<result; i++ )
      _cprintf_s( "%i ", n[i] );
   _cprintf_s( "\r\n" );
}
```

```Input
1 2 3
```

```Output
You entered 1 2 3
```

## <a name="see-also"></a>Ayrıca bkz.

[Konsol ve bağlantı noktası g/ç](../../c-runtime-library/console-and-port-i-o.md)<br/>
[_cprintf, _cprintf_l, _cwprintf, _cwprintf_l](cprintf-cprintf-l-cwprintf-cwprintf-l.md)<br/>
[fscanf_s, _fscanf_s_l, fwscanf_s, _fwscanf_s_l](fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md)<br/>
[scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)<br/>
[sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l](sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)<br/>
