---
title: mbstowcs_s, _mbstowcs_s_l
ms.date: 4/2/2020
api_name:
- _mbstowcs_s_l
- mbstowcs_s
- _o__mbstowcs_s_l
- _o_mbstowcs_s
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
- api-ms-win-crt-convert-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _mbstowcs_s_l
- mbstowcs_s
helpviewer_keywords:
- _mbstowcs_s_l function
- mbstowcs_s function
- mbstowcs_s_l function
ms.assetid: 2fbda953-6918-498f-b440-3e7b21ed65a4
ms.openlocfilehash: 07d694a7430f23e2f9600a5d2b147bcee2ef0e09
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338804"
---
# <a name="mbstowcs_s-_mbstowcs_s_l"></a>mbstowcs_s, _mbstowcs_s_l

Çok bayt karakter dizisini karşılık gelen geniş karakter dizisine dönüştürür. [CRT](../../c-runtime-library/security-features-in-the-crt.md)Güvenlik Özellikleri açıklandığı gibi güvenlik geliştirmeleri ile [_mbstowcs_l mbstowcs](mbstowcs-mbstowcs-l.md) sürümleri.

## <a name="syntax"></a>Sözdizimi

```C
errno_t mbstowcs_s(
   size_t *pReturnValue,
   wchar_t *wcstr,
   size_t sizeInWords,
   const char *mbstr,
   size_t count
);
errno_t _mbstowcs_s_l(
   size_t *pReturnValue,
   wchar_t *wcstr,
   size_t sizeInWords,
   const char *mbstr,
   size_t count,
   _locale_t locale
);
template <size_t size>
errno_t mbstowcs_s(
   size_t *pReturnValue,
   wchar_t (&wcstr)[size],
   const char *mbstr,
   size_t count
); // C++ only
template <size_t size>
errno_t _mbstowcs_s_l(
   size_t *pReturnValue,
   wchar_t (&wcstr)[size],
   const char *mbstr,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parametreler

*pReturnValue*<br/>
Dönüştürülen karakter sayısı.

*Wcstr*<br/>
Dönüştürülen geniş karakter dizesi için arabellek adresi.

*sizeInWords*<br/>
Kelimelerde *wcstr* arabelleği boyutu.

*mbstr*<br/>
Null sonlandırılmış çok bayt karakter dizisinin adresi.

*Sayısı*<br/>
Null veya [_TRUNCATE](../../c-runtime-library/truncate.md)sonlandırma dahil değil, *wcstr* arabellekte depolanması için geniş karakter maksimum sayısı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Sıfır başarılı, hata bir hata kodu.

|Hata koşulu|İade değeri ve **errno**|
|---------------------|------------------------------|
|*wcstr* **NULL** ve *sizeInWords* > 0|**Eınval**|
|*mbstr* **NULL** olduğunu|**Eınval**|
|Hedef arabellek dönüştürülen dizeyi içeremeyecek kadar küçüktür *(sayım* **_TRUNCATE**sürece ; aşağıdaki Açıklamalar'a bakın)|**Erange**|
|*wcstr* **NULL** ve *sizeInWords* == 0 değildir|**Eınval**|

Bu koşullardan herhangi biri oluşursa, geçersiz parametre özel durumu [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md) açıklandığı gibi çağrılır. Yürütmenin devam etmesine izin verilirse, işlev bir hata kodu döndürür ve tabloda belirtildiği gibi **errno** ayarlar.

## <a name="remarks"></a>Açıklamalar

**mbstowcs_s** işlevi, *mbstr* tarafından işaret edilen çok bayt karakter dizesini, *wcstr'in*işaret ettiği arabellekte depolanan geniş karakterlere dönüştürür. Dönüştürme, bu koşullardan biri karşılanana kadar her karakter için devam edecektir:

- Çok baytlı null karakterle karşılaşılır

- Geçersiz bir çok bayt karakteriyle karşılaşılır

- *Wcstr* arabelleğinde depolanan geniş karakter sayısı *eşittir sayısı.*

Hedef dize her zaman null-sonlandırıldı (bir hata durumunda bile).

*Sayım* [_TRUNCATE](../../c-runtime-library/truncate.md)özel bir değerse, **mbstowcs_s,** null terminator için yer bırakırken, hedef arabelleğe sığacak kadar dize dönüştürür.

**mbstowcs_s** kaynak dizesini başarıyla dönüştürürse, boyutu dönüştürülmüş dizenin geniş karakterlerine, null terminator'u da içeren geniş karakterlere, *&#42;pReturnValue'e* koyar (sağlanan *pReturnValue* **NULL**değildir). Bu, *wcstr* bağımsız değişkeni **NULL** olsa bile oluşur ve gerekli arabellek boyutunu belirlemek için bir yol sağlar. *WCSTR* **NULL** *ise, sayım* yoksayılır ve *sizeInWords* 0 olmalıdır unutmayın.

**mbstowcs_s** geçersiz bir multibayt karakter le karşılaşırsa,&#42;*pReturnValue*0 koyar, boş bir dize hedef arabellek ayarlar, **EILSEQ** **için errno** ayarlar ve **EILSEQ**döndürür .

*Mbstr* ve *wcstr* ile işaret edilen diziler çakışıyorsa, **mbstowcs_s** davranışı tanımsızdır.

> [!IMPORTANT]
> Wcstr ve *mbstr'nin* çakışmadığından ve bu *wcstr* *sayımda* dönüştürülecek çok bayt karakter sayısını doğru şekilde yansıttığından emin olun.

**mbstowcs_s,** yerele bağımlı herhangi bir davranış için geçerli yerel durumu kullanır; **_mbstowcs_s_l,** bunun yerine geçirilen yerel alanı kullanması dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

C++'da, bu işlevleri kullanmak şablon aşırı yükleri ile basitleştirilir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkartabilir (boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırabilir) ve eski, güvenli olmayan işlevleri yeni, güvenli karşılıklarıyla otomatik olarak değiştirebilirler. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**mbstowcs_s**|\<stdlib.h>|
|**_mbstowcs_s_l**|\<stdlib.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[MultiByteToWideChar](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
