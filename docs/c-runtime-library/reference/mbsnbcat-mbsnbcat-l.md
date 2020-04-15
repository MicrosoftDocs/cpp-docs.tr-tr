---
title: _mbsnbcat, _mbsnbcat_l
ms.date: 4/2/2020
api_name:
- _mbsnbcat_l
- _mbsnbcat
- _o__mbsnbcat
- _o__mbsnbcat_l
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
- mbsnbcat
- mbsnbcat_l
- _mbsnbcat
- _mbsnbcat_l
helpviewer_keywords:
- tcsncat_l function
- _tcsncat function
- mbsnbcat_l function
- mbsnbcat function
- _mbsnbcat_l function
- _tcsncat_l function
- _mbsnbcat function
- tcsncat function
ms.assetid: aa0f1d30-0ddd-48d1-88eb-c6884b20fd91
ms.openlocfilehash: 7598b20db4698ff8f95fbcefa00864be1b958447
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81340811"
---
# <a name="_mbsnbcat-_mbsnbcat_l"></a>_mbsnbcat, _mbsnbcat_l

Ekler, en fazla, başka bir multibayt karakter dize ilk **n** bayt. Bu işlevlerin daha güvenli sürümleri mevcuttur; [_mbsnbcat_s, _mbsnbcat_s_l](mbsnbcat-s-mbsnbcat-s-l.md)bakın.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
unsigned char *_mbsnbcat(
   unsigned char *dest,
   const unsigned char *src,
   size_t count
);
unsigned char *_mbsnbcat_l(
   unsigned char *dest,
   const unsigned char *src,
   size_t count,
   _locale_t locale
);
template <size_t size>
unsigned char *_mbsnbcat(
   unsigned char (&dest)[size],
   const unsigned char *src,
   size_t count
); // C++ only
template <size_t size>
unsigned char *_mbsnbcat_l(
   unsigned char (&dest)[size],
   const unsigned char *src,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parametreler

*Dest*<br/>
Null-sonlandırılan çok bayt karakterli hedef dize.

*src*<br/>
Null-sonlandırılan multibyt karakter kaynak dizesi.

*Sayısı*<br/>
*Src'den* *dest'e*ek bayt sayısı.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

**_mbsnbcat** hedef dize için bir işaretçi döndürür. Bir hatayı belirtmek için hiçbir iade değeri ayrılmıştır.

## <a name="remarks"></a>Açıklamalar

**_mbsnbcat** işlevi ekler, en fazla, *dest* *src* ilk *sayısı* bayt . *Dest'teki* null karakterinhemen önündeki bayt bir kurşun bayt ise, *src'nin* baş baytı bu kurşun baytının üzerine yazar. Aksi takdirde, *src'nin* ilk baytdede *destin*sonlandırıcı null karakterini yazar. *Sayım* baytları eklenmeden önce *src'de* bir null bayt görünürse, **_mbsnbcat** *src'den*null karaktere kadar tüm baytları ekler. *Sayım* *src*uzunluğundan büyükse, *sayım*yerine *src* uzunluğu kullanılır. Elde edilen dize null bir karakterle sonlandırılır. Kopyalama çakışan dizeleri arasında gerçekleşirse, davranış tanımsız.

Çıktı değeri, yerel LC_CTYPE **kategori** ayarı ayarı etkilenir; daha fazla bilgi için [setlocale'ye](setlocale-wsetlocale.md) bakın. İşlevin **_mbsnbcat** sürümü, bu yerele bağımlı davranış için geçerli yerel durumu kullanır; **_mbsnbcat_l** sürümü, bunun yerine geçirilen yerel parametreyi kullanmaları dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

**Güvenlik Notu** Null-terminatedli dize kullanın. Null-sonlandırılan dize hedef arabellek boyutunu aşmamalıdır. Daha fazla bilgi için [bkz.](/windows/win32/SecBP/avoiding-buffer-overruns)

*Dest* veya *src* **NULL**ise, işlev [Parametre Doğrulama](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz bir parametre hatası oluşturur. Hata işlenirse, işlev **EINVAL** döndürür ve **EINVAL** **için errno** ayarlar.

C++'da, bu işlevlerin daha yeni ve güvenli karşıtlarını çağıran şablon aşırı yüklemeleri vardır. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsncat**|[strncat](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|**_mbsnbcat**|[wcsncat](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)|
|**_tcsncat_l**|**_strncat_l**|**_mbsnbcat_l**|**_wcsncat_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbsnbcat**|\<mbstring.h>|
|**_mbsnbcat_l**|\<mbstring.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_strncnt, _wcsncnt, _mbsnbcnt, _mbsnbcnt_l, _mbsnccnt, _mbsnccnt_l](strncnt-wcsncnt-mbsnbcnt-mbsnbcnt-l-mbsnccnt-mbsnccnt-l.md)<br/>
[_mbsnbcpy, _mbsnbcpy_l](mbsnbcpy-mbsnbcpy-l.md)<br/>
[_mbsnbicmp, _mbsnbicmp_l](mbsnbicmp-mbsnbicmp-l.md)<br/>
[_mbsnbset, _mbsnbset_l](mbsnbset-mbsnbset-l.md)<br/>
[strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[_mbsnbcat_s, _mbsnbcat_s_l](mbsnbcat-s-mbsnbcat-s-l.md)<br/>
