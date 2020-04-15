---
title: _mbccpy_s, _mbccpy_s_l
ms.date: 4/2/2020
api_name:
- _mbccpy_s
- _mbccpy_s_l
- _o__mbccpy_s
- _o__mbccpy_s_l
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
- _mbccpy_s_l
- mbccpy_s_l
- mbccpy_s
- _mbccpy_s
helpviewer_keywords:
- tccpy_s_l function
- _tccpy_s function
- _mbccpy_s function
- mbccpy_s function
- tccpy_s function
- mbccpy_s_l function
- _tccpy_s_l function
- _mbccpy_s_l function
ms.assetid: b6e965fa-53c1-4ec3-85ef-a1c4b4f2b2da
ms.openlocfilehash: 08df395c6978c84b3f53ed0b07ce988afd0249f6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341241"
---
# <a name="_mbccpy_s-_mbccpy_s_l"></a>_mbccpy_s, _mbccpy_s_l

Bir çok bayt karakteri bir dizeden başka bir dize kopyalar. [CRT'deki](mbccpy-mbccpy-l.md) [Güvenlik Özellikleri'nde](../../c-runtime-library/security-features-in-the-crt.md)açıklandığı gibi, _mbccpy _mbccpy_l bu sürümlerinde güvenlik geliştirmeleri vardır.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _mbccpy_s(
   unsigned char *dest,
   size_t buffSizeInBytes,
   int * pCopied,
   const unsigned char *src
);
errno_t _mbccpy_s_l(
   unsigned char *dest,
   size_t buffSizeInBytes,
   int * pCopied,
   const unsigned char *src,
   locale_t locale
);
template <size_t size>
errno_t _mbccpy_s(
   unsigned char (&dest)[size],
   int * pCopied,
   const unsigned char *src
); // C++ only
template <size_t size>
errno_t _mbccpy_s_l(
   unsigned char (&dest)[size],
   int * pCopied,
   const unsigned char *src,
   locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parametreler

*Dest*<br/>
Hedefi kopyalayın.

*buffSizeBytes*<br/>
Hedef arabelleğe boyutu.

*pFotokopi*<br/>
Kopyalanan bayt sayısıyla doldurulur (başarılı olursa 1 veya 2). Numarayı umursamıyorsanız **NULL'u** geçirin.

*src*<br/>
Kopyalanması gereken çok bayt karakter.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır; hata bir hata kodu. *src* veya *dest* **NULL**ise , ya da **buffSizeinBytes** bayt daha fazla *dest*kopyalanır, sonra geçersiz parametre işleyicisi çağrılır, [Parametre Doğrulama](../../c-runtime-library/parameter-validation.md)açıklandığı gibi . Yürütmedevam etmesine izin verilirse, işlevleri **EINVAL** dönmek ve **errno** **EINVAL**ayarlanır.

## <a name="remarks"></a>Açıklamalar

**_mbccpy_s** işlevi *src* den *dest*bir multibayt karakter kopyalar. *Eğer src,* [_ismbblead](ismbblead-ismbblead-l.md)için örtülü bir çağrı ile belirlenen çok baytlık bir karakterin kurşun baytını işaret etmiyorsa, *src'nin* işaret ettiği tek bayt kopyalanır. *Src* bir kurşun bayt puan ancak aşağıdaki bayt 0 ve böylece geçersiz ise, o zaman 0 *dest*kopyalanır , **errno** **EILSEQ**ayarlanır , ve fonksiyon **EILSEQ**döndürür .

**_mbccpy_s** hükümsüz bir sonlandırıcı yı eklemiyor; ancak, *src* null bir karaktere işaret ediyorsa, o zaman null *dest* kopyalanır (bu sadece normal bir tek bayt kopya).

*pCopied* değeri kopyalanan bayt sayısı ile doldurulur. İşlem başarılı olursa olası değerler 1 ve 2'dir. **NULL** geçirilirse, bu parametre yoksayılır.

|*src*|*dest* kopyalanır|*pFotokopi*|Döndürülen değer|
|-----------|----------------------|---------------|------------------|
|kurşun-bayt olmayan|kurşun-bayt olmayan|1|0|
|0|0|1|0|
|kurşun-byte olmayan 0 takip|kurşun-byte olmayan 0 takip|2|0|
|kurşun-byte ardından 0|0|1|**Eılseq**|

İkinci satırın ilkinin özel bir örneği olduğunu unutmayın. Ayrıca tablo *buffSizeBytes* >= *pCopied*varsayar unutmayın.

**_mbccpy_s,** yerel e-eşe bağlı herhangi bir davranış için geçerli yerel alanı kullanır. **_mbccpy_s_l,** **_mbccpy_s_l'nin** herhangi bir yerele bağımlı davranış için geçirilen yerelliği kullanması dışında **_mbccpy_s** ile aynıdır.

C++'da, bu işlevleri kullanmak şablon aşırı yükleri ile basitleştirilir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkararak boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırabilir. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tccpy_s**|Makro veya satır çizgisi işleviyle eşler.|**_mbccpy_s**|Makro veya satır çizgisi işleviyle eşler.|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbccpy_s**|\<mbstring.h>|
|**_mbccpy_s_l**|\<mbstring.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
