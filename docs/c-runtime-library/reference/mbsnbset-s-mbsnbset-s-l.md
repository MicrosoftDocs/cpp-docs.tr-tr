---
title: _mbsnbset_s, _mbsnbset_s_l
ms.date: 4/2/2020
api_name:
- _mbsnbset_s_l
- _mbsnbset_s
- _o__mbsnbset_s
- _o__mbsnbset_s_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- mbsnbset_s
- _mbsnbset_s_l
- _mbsnbset_s
- mbsnbset_s_l
helpviewer_keywords:
- tcsnset_s function
- mbsnbset_s function
- mbsnbset_s_l function
- _mbsnbset_s_l function
- _tcsnset_s_l function
- _mbsnbset_s function
- _tcsnset_s function
- tcsnset_s_l function
ms.assetid: 811f92c9-cc31-4bbd-8017-2d1bfc6fb96f
ms.openlocfilehash: 0ecfac1f9c0f1f9aeb8de85411b0b2f696b578e2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81339016"
---
# <a name="_mbsnbset_s-_mbsnbset_s_l"></a>_mbsnbset_s, _mbsnbset_s_l

Çok bayt karakterli dizedeki ilk **n** baytlarını belirli bir karaktere ayarlar. [CRT'deki](mbsnbset-mbsnbset-l.md) [Güvenlik Özellikleri'nde](../../c-runtime-library/security-features-in-the-crt.md)açıklandığı gibi, _mbsnbset _mbsnbset_l bu sürümlerinde güvenlik geliştirmeleri vardır.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _mbsnbset_s(
   unsigned char *str,
   size_t size,
   unsigned int c,
   size_t count
);
errno_t _mbsnbset_s_l(
   unsigned char *str,
   size_t size,
   unsigned int c,
   size_t count,
   _locale_t locale
);
template <size_t size>
errno_t _mbsnbset_s(
   unsigned char (&str)[size],
   unsigned int c,
   size_t count
); // C++ only
template <size_t size>
errno_t _mbsnbset_s_l(
   unsigned char (&str)[size],
   unsigned int c,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parametreler

*Str*<br/>
Dize değiştirilecek.

*Boyutu*<br/>
Dize arabelleği boyutu.

*C*<br/>
Tek bayt veya çok bayt karakterli ayar.

*Sayısı*<br/>
Ayarlanacak bayt sayısı.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır; aksi takdirde, bir hata kodu.

## <a name="remarks"></a>Açıklamalar

**_mbsnbset_s** ve **_mbsnbset_s_l** fonksiyonları, en fazla, *str* c ilk *c* *sayısı* bayt ayarlayın. *Sayım* *str*uzunluğundan büyükse, *str* uzunluğu *sayı*yerine kullanılır. *C* çok bayt karakterse ve *sayıyla*belirtilen son bayta tamamen ayarlanamıyorsa, son bayt boş bir karakterle tamamlanır. **_mbsnbset_s** ve **_mbsnbset_s_l** *str*sonunda bir sonlandırıcı null yer yok.

**_mbsnbset_s** ve **_mbsnbset_s_l** **_mbsnset**benzer , onlar *c*karakter *saymak* yerine *bayt saymak* dışında .

*str* **NULL** ise veya *sayı* sıfır ise, bu işlev [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz bir parametre özel durumu oluşturur. Yürütmedevam etmesine izin verilirse, **errno** **EINVAL** olarak ayarlanır ve işlev **NULL**döndürür. Ayrıca, *c* geçerli bir çok bayt karakter değilse, **errno** **EINVAL** olarak ayarlanır ve bunun yerine bir boşluk kullanılır.

Çıktı değeri, yerel LC_CTYPE **kategori** ayarı ayarı etkilenir; daha fazla bilgi için [setlocale, _wsetlocale](setlocale-wsetlocale.md) bakın. Bu işlevin **_mbsnbset_s** sürümü, bu yerele bağımlı davranış için geçerli yerel durumu kullanır; **_mbsnbset_s_l** sürümü, bunun yerine geçirilen yerel parametreyi kullanması dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

C++'da, bu işlevlerin kullanımı şablon aşırı yükleri ile basitleştirilir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabiliyor ve bu şekilde boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırabilir. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

Bu işlevlerin hata ayıklama kitaplığı sürümleri önce arabelleği 0xFE ile doldurur. Bu davranışı devre dışı kullanabilirsiniz, [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsnset_s**|**_strnset_s**|**_mbsnbset_s**|**_wcsnset_s**|
|**_tcsnset_s_l**|`_strnset_s _l`|**_mbsnbset_s_l**|**_wcsnset_s_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbsnbset_s**|\<mbstring.h>|
|**_mbsnbset_s_l**|\<mbstring.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_mbsnbset_s.c
#include <mbstring.h>
#include <stdio.h>

int main( void )
{
   char string[15] = "This is a test";
   /* Set not more than 4 bytes of string to be *'s */
   printf( "Before: %s\n", string );
   _mbsnbset_s( string, sizeof(string), '*', 4 );
   printf( "After:  %s\n", string );
}
```

## <a name="output"></a>Çıktı

```Output
Before: This is a test
After:  **** is a test
```

## <a name="see-also"></a>Ayrıca bkz.

[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_strnset, _strnset_l, _wcsnset, _wcsnset_l, _mbsnset, _mbsnset_l](strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
