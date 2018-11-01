---
title: _mbsnbset, _mbsnbset_l
ms.date: 11/04/2016
apiname:
- _mbsnbset
- _mbsnbset_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mbsnbset
- mbsnbset_l
- _mbsnbset
- _mbsnbset_l
helpviewer_keywords:
- tcsnset function
- _tcsnset_l function
- _mbsnbset function
- _tcsnset function
- _mbsnbset_l function
- mbsnbset_l function
- tcsnset_l function
- mbsnbset function
ms.assetid: 8e46ef75-9a56-42d2-a522-a08450c67c19
ms.openlocfilehash: 4c0f053cde32d71e4864c442b761606bb56c8829
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50484623"
---
# <a name="mbsnbset-mbsnbsetl"></a>_mbsnbset, _mbsnbset_l

İlk Ayarlar **n** bayt sayısı için belirtilen bir karakterin çok baytlı karakterli bir dizedir. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz: [_mbsnbset_s, _mbsnbset_s_l](mbsnbset-s-mbsnbset-s-l.md).

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
unsigned char *_mbsnbset(
   unsigned char *str,
   unsigned int c,
   size_t count
);
unsigned char *_mbsnbset_l(
   unsigned char *str,
   unsigned int c,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Değiştirilecek dize.

*c*<br/>
Tek baytlı veya çok baytlı karakter ayarı.

*Sayısı*<br/>
Ayarlanacak bayt sayısı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_mbsnbset** değiştirilen dizeye bir işaretçi döndürür.

## <a name="remarks"></a>Açıklamalar

**_Mbsnbset** ve **_mbsnbset_l** işlevler kümesi, en çok ilk *sayısı* bayt *str* için *c*. Varsa *sayısı* uzunluğundan büyükse *str*, uzunluğunu *str* yerine kullanılan *sayısı*. Varsa *c* çok baytlı bir karakterse ve tarafından belirtilen son bayrak tamamen içine ayarlanamaz *sayısı*, son bayt bir boş karakterle doldurulur. **_mbsnbset** ve **_mbsnbset_l** bir sonlandırma yerleştirmez sonunda null *str*.

**_mbsnbset** ve **_mbsnbset_l** benzer **_mbsnset**, ayarlaması dışında *sayısı* bayt yerine *sayısı* karakter *c*.

Varsa *str* olduğu **NULL** veya *sayısı* sıfırsa bu işlev açıklandığı gibi geçersiz parametre özel durum oluşturur [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **errno** ayarlanır **EINVAL** ve işlev döndürür **NULL**. Ayrıca, varsa *c* geçerli çok baytlı bir karakter değil **errno** ayarlanır **EINVAL** ve boşluk yerine kullanılır.

Çıkış değeri ayarından etkilenir **LC_CTYPE** yerel ayarının kategori ayarına; bkz: [setlocale](setlocale-wsetlocale.md) daha fazla bilgi için. **_Mbsnbset** sürümü bu işlevin, bu yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır **_mbsnbset_l** sürümü, bu kullanmalarıdır bunun yerine iletilmiş yerel ayar parametresini aynıdır. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

**Güvenlik Notu** bu API, bir arabellek taşması sorunu duruma olası bir tehdit artmasına neden olur. Arabellek taşması sorunları, sistem saldırı, bir unwarranted ayrıcalık yükseltilmesi ile sonuçlanan sık kullanılan bir yöntemdir. Daha fazla bilgi için [arabellek taşmalarını](/windows/desktop/SecBP/avoiding-buffer-overruns).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsnset**|**_strnset**|**_mbsnbset**|**_wcsnset**|
|**_tcsnset_l**|**_strnset_l**|**_mbsnbset_l**|**_wcsnset_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbsnbset**|\<Mbstring.h >|
|**_mbsnbset_l**|\<Mbstring.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_mbsnbset.c
// compile with: /W3
#include <mbstring.h>
#include <stdio.h>

int main( void )
{
   char string[15] = "This is a test";
   /* Set not more than 4 bytes of string to be *'s */
   printf( "Before: %s\n", string );
   _mbsnbset( string, '*', 4 ); // C4996
   // Note; _mbsnbset is deprecated; consider _mbsnbset_s
   printf( "After:  %s\n", string );
}
```

### <a name="output"></a>Çıkış

```Output
Before: This is a test
After:  **** is a test
```

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_strnset, _strnset_l, _wcsnset, _wcsnset_l, _mbsnset, _mbsnset_l](strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
