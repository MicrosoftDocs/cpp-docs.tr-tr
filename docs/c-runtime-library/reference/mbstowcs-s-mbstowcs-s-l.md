---
title: mbstowcs_s, _mbstowcs_s_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbstowcs_s_l
- mbstowcs_s
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _mbstowcs_s_l
- mbstowcs_s
dev_langs:
- C++
helpviewer_keywords:
- _mbstowcs_s_l function
- mbstowcs_s function
- mbstowcs_s_l function
ms.assetid: 2fbda953-6918-498f-b440-3e7b21ed65a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a3457195b07335345476153038d7ab38606607a2
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43217365"
---
# <a name="mbstowcss-mbstowcssl"></a>mbstowcs_s, _mbstowcs_s_l

Çok baytlı bir karakter dizisi bir karşılık gelen geniş karakter dizisine dönüştürür. Sürümleri [mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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
Dönüştürülecek karakter sayısı.

*wcstr*<br/>
Arabellek için ortaya çıkan dönüştürülmüş geniş karakter dizesi adresi.

*sizeInWords*<br/>
Boyutu *wcstr* sözcükleri arabellek.

*mbstr*<br/>
Çok baytlı karakter dizisi null adresini sonlandırıldı.

*Sayısı*<br/>
Depolamak için geniş karakterlerin sayısı *wcstr* arabellek, sonlandırıcı null içermeden veya [_TRUNCATE](../../c-runtime-library/truncate.md).

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır, bir hata kodu.

|Hata koşulu|Dönüş değeri ve **errno**|
|---------------------|------------------------------|
|*wcstr* olduğu **NULL** ve *sizeInWords* > 0|**EINVAL**|
|*mbstr* olduğu **NULL**|**EINVAL**|
|Hedef arabelleğinin içeren dönüştürülmüş dize çok küçük (sürece *sayısı* olduğu **_TRUNCATE**; aşağıdaki açıklamalara bakın)|**ERANGE**|
|*wcstr* değil **NULL** ve *sizeInWords* == 0|**EINVAL**|

Bu koşullardan herhangi biri meydana gelirse, açıklanan şekilde geçersiz parametre özel durumu çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md) . Yürütme devam etmesine izin verilirse işlev bir hata kodu döndürür ve ayarlar **errno** tabloda belirtildiği şekilde.

## <a name="remarks"></a>Açıklamalar

**Mbstowcs_s** işlevi dönüştürür bir işaret ettiği çok baytlı karakter dizesi *mbstr* tarafından işaret edilen arabellek içinde depolanan geniş karakterlerin içine *wcstr*. Dönüştürme, her karakter için şu koşullardan biri karşılandığında kadar devam eder:

- Çok baytlı bir null karakteri ile karşılaşıldı

- Geçersiz bir çok baytlı karakter karşılaşıldı

- İçinde depolanan geniş karakterlerin sayısını *wcstr* arabellek eşittir *sayısı*.

Hedef dize her zaman null ile sonlandırılmış (bile bir hata olması durumunda).

Varsa *sayısı* özel değer [_TRUNCATE](../../c-runtime-library/truncate.md), ardından **mbstowcs_s** büyük bir işlem olarak dize dönüştürür yine de bir null yer bırakarak hedef arabellek içine Sığdır Sonlandırıcı.

Varsa **mbstowcs_s** başarılı bir şekilde kaynak dizesini dönüştürür dönüştürülmüş dize halinde null sonlandırıcıyı da dahil olmak üzere, geniş karakter cinsinden boyutu koyar  *&#42;pReturnValue* ( sağlanan*pReturnValue* değil **NULL**). Bu meydana bile *wcstr* bağımsız değişkeni **NULL** ve gerekli arabellek boyutunu belirlemek için bir yol sağlar. Unutmayın *wcstr* olduğu **NULL**, *sayısı* göz ardı edilir ve *sizeInWords* 0 olmalıdır.

Varsa **mbstowcs_s** geçersiz bir çok baytlı karakter karşılaştığında 0 koyar  *&#42;pReturnValue*, için boş bir dize hedef arabelleğinin ayarlar, ayarlar **errno** için **EILSEQ**ve döndürür **EILSEQ**.

Dizileri işaret ettiği varsa *mbstr* ve *wcstr* üst üste, davranışını **mbstowcs_s** tanımsızdır.

> [!IMPORTANT]
> Emin *wcstr* ve *mbstr* örtüşmeyen ve *sayısı* doğru şekilde dönüştürmek için çok baytlı karakter sayısını yansıtır.

**mbstowcs_s** herhangi bir yerel ayara bağımlı davranış için; geçerli yerel ayarı kullanır **_mbstowcs_s_l** bunun yerine iletilmiş yerel ayarı kullanması dışında aynıdır. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

C++ dilinde bu işlevlerin kullanılması şablon aşırı yüklemeleriyle basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir (bir boyut bağımsız değişkeni belirtme gereksinimi ortadan kalkar) ve bunlar otomatik olarak eski ve güvenli olmayan işlevlerle daha yeni ve güvenli karşılıklarını değiştirir. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**mbstowcs_s**|\<stdlib.h >|
|**_mbstowcs_s_l**|\<stdlib.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[MultiByteToWideChar](/windows/desktop/api/stringapiset/nf-stringapiset-multibytetowidechar)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
