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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 4a6e86e1122a7392862fa34a59042c32560fd69d
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82915460"
---
# <a name="mbstowcs_s-_mbstowcs_s_l"></a>mbstowcs_s, _mbstowcs_s_l

Çok baytlı karakterlerden oluşan bir diziyi karşılık gelen geniş karakter dizisine dönüştürür. [Mbstowcs sürümleri,](mbstowcs-mbstowcs-l.md) [CRT içindeki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleriyle _mbstowcs_l.

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

*Ön kapatma değeri*<br/>
Dönüştürülen karakterlerin sayısı.

*wcstr*<br/>
Elde edilen dönüştürülmüş geniş karakter dizesi için arabelleğin adresi.

*sizeInWords*<br/>
Sözcükteki *wcstr* arabelleğinin boyutu.

*mbstr*<br/>
Null ile sonlandırılmış çok baytlı karakterlerin bir dizisinin adresi.

*biriktirme*<br/>
*Wcstr* arabelleğinde depolanacak, Sonlandırıcı null veya [_TRUNCATE](../../c-runtime-library/truncate.md)dahil olmayan en fazla geniş karakter sayısı.

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır, hata durumunda hata kodu.

|Hata koşulu|Dönüş değeri ve **errno**|
|---------------------|------------------------------|
|*wcstr* **null** ve *sizeInWords* > 0|**EıNVAL**|
|*mbstr* **null**|**EıNVAL**|
|Hedef arabellek dönüştürülmüş dizeyi ( *sayı* **_TRUNCATE**olmadığı müddetçe) çok küçük. aşağıdaki açıklamalara bakın)|**ERANGE**|
|*wcstr* **null** ve *sizeInWords* = = 0 değil|**EıNVAL**|

Bu koşullardan herhangi biri gerçekleşirse, geçersiz parametre özel durumu [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md) açıklandığı gibi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, işlev bir hata kodu döndürür ve tabloda belirtilen **errno** değerini ayarlar.

## <a name="remarks"></a>Açıklamalar

**Mbstowcs_s** işlevi, *mbstr* tarafından işaret edilen çok baytlı karakterlerden oluşan dizeyi, *wcstr*tarafından işaret edilen arabellekte depolanan geniş karakterlere dönüştürür. Bu koşullardan biri karşılanana kadar dönüştürme her karakter için devam eder:

- Çok baytlı null karakter ile karşılaşıldı

- Geçersiz çok baytlı bir karakter ile karşılaşıldı

- *Wcstr* arabelleğinde depolanan geniş karakterlerin sayısı eşittir *Count*.

Hedef dize her zaman null ile sonlandırılır (bir hata durumunda bile).

*Count* değeri [_TRUNCATE](../../c-runtime-library/truncate.md)özel değer ise, **mbstowcs_s** , dizenin büyük bir kısmını hedef arabelleğe sığdıracak şekilde dönüştürür.

Kaynak dizeyi başarıyla dönüştürülürse **mbstowcs_s** , null Sonlandırıcı dahil olmak üzere, dönüştürülmüş dizenin geniş karakterlere, *&#42;pReturnValue* (belirtilen *pReturnValue* **null**değil) değerini koyar. Bu durum, *wcstr* bağımsız değişkeni **null** olsa da, gerekli arabellek boyutunu belirlemede bir yol sağlar. *Wcstr* **null**ise, *Count* yok sayılır ve *sizeInWords* 0 olmalıdır.

**Mbstowcs_s** geçersiz bir çok baytlı karakterle karşılaşırsa, 0 ' ı *&#42;pReturnValue*' a koyar, hedef arabelleği boş bir dizeye ayarlar, **errno** 'u **eilseq**olarak ayarlar ve **eilseq**döndürür.

*Mbstr* ve *wcstr* tarafından işaret edilen sıralar çakışırsa **mbstowcs_s** davranışı tanımsızdır.

> [!IMPORTANT]
> *Wcstr* ve *mbstr* 'in çakışmadığından ve bu *sayının* dönüştürülecek çok baytlı karakterlerin sayısını doğru yansıttığından emin olun.

**mbstowcs_s** , yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır; **_mbstowcs_s_l** , bunun yerine geçirilen yerel ayarı kullanması dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

C++ ' da, bu işlevlerin kullanılması şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir (bir boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırır) ve eski, güvenli olmayan işlevleri otomatik olarak yeni, güvenli karşılıklarıyla değiştirebilir. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**mbstowcs_s**|\<Stdlib. h>|
|**_mbstowcs_s_l**|\<Stdlib. h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Ayarlar](../../c-runtime-library/locale.md)<br/>
[MultiByteToWideChar](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
