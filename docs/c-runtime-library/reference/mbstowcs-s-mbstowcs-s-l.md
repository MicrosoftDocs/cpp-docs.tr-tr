---
title: mbstowcs_s, _mbstowcs_s_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
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
caps.latest.revision: 31
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1af00649bf6aca91877c55d5df1d27eb0579275e
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="mbstowcss-mbstowcssl"></a>mbstowcs_s, _mbstowcs_s_l

Birden çok baytlı karakter dizisi geniş karakterler karşılık gelen bir dizi dönüştürür. Sürümleri [mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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

*wcstr*<br/>
Ortaya çıkan dönüştürülmüş geniş karakter dizesi için arabellek adresi.

*sizeInWords*<br/>
Boyutunu *wcstr* sözcükler arabellek.

*mbstr*<br/>
Boş bir dizi adresini birden çok baytlı karakterler sonlandırıldı.

*Sayısı*<br/>
En fazla depolamak üzere geniş karakter sayısını *wcstr* arabellek, sonlandırma null dahil değil veya [_TRUNCATE](../../c-runtime-library/truncate.md).

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Sıfır başarılı olursa, hatasında bir hata kodu.

|Hata durumu|Dönüş değeri ve **errno**|
|---------------------|------------------------------|
|*wcstr* olan **NULL** ve *sizeInWords* > 0|**EINVAL**|
|*mbstr* olan **NULL**|**EINVAL**|
|Hedef arabellek dönüştürülmüş dizeyi içeren için çok küçük. (sürece *sayısı* olan **_TRUNCATE**; açıklamalar aşağıya bakın)|**ERANGE**|
|*wcstr* değil **NULL** ve *sizeInWords* == 0|**EINVAL**|

Bu koşulların herhangi biri meydana gelirse, geçersiz bir parametre özel durum açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md) . Devam etmek için yürütülmesine izin veriliyorsa, bir hata kodu işlevi döndürür ve ayarlar **errno** tabloda belirtildiği şekilde.

## <a name="remarks"></a>Açıklamalar

**Mbstowcs_s** işlevi dönüştürür gösterdiği birden çok baytlı karakter dizesi *mbstr* gösterdiği arabellek depolanan geniş karakterler içine *wcstr*. Bu koşullardan biri yerine getirilene kadar dönüştürme için her karakter devam eder:

- Birden çok baytlı null karakteri ile karşılaşıldı

- Geçersiz bir birden çok baytlı karakter karşılaştı

- Depolanan geniş karakter sayısını *wcstr* arabellek eşittir *sayısı*.

Hedef dize her zaman null (bile bir hata olması durumunda) sonlandırılır.

Varsa *sayısı* özel değer [_TRUNCATE](../../c-runtime-library/truncate.md), ardından **mbstowcs_s** dize olarak büyük dönüştürür hala null yer bırakarak hedef arabelleğine sığacak Sonlandırıcı.

Varsa **mbstowcs_s** başarıyla kaynak dizesi dönüştürür dönüştürülen dizenin içine null Sonlandırıcı dahil olmak üzere geniş karakter cinsinden boyutu koyar  *&#42;pReturnValue* ( sağlanan*pReturnValue* değil **NULL**). Bu meydana olsa bile *wcstr* bağımsız değişkeni **NULL** ve gerekli arabellek boyutunu belirlemek için bir yol sağlar. Unutmayın *wcstr* olan **NULL**, *sayısı* göz ardı edilir ve *sizeInWords* 0 olmalıdır.

Varsa **mbstowcs_s** geçersiz bir birden çok baytlı karakter karşılaştığında 0 koyar  *&#42;pReturnValue*, hedef arabelleği boş bir dize olarak ayarlar, ayarlar **errno** için **EILSEQ**ve döndürür **EILSEQ**.

Dizileri gösterdiği varsa *mbstr* ve *wcstr* üst üste, davranışını **mbstowcs_s** tanımlanmadı.

> [!IMPORTANT]
> Emin *wcstr* ve *mbstr* çakışmaması ve *sayısı* doğru şekilde dönüştürmek için birden çok baytlı karakter sayısını yansıtır.

**mbstowcs_s** geçerli yerel ayar için tüm yerel ayara bağımlı davranışı; kullanır **_mbstowcs_s_l** yerine geçirilen yerel ayar kullandığı dışında aynıdır. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

C++'da, bu işlevler kullanılarak şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı arabellek uzunluğu otomatik olarak Infer (boyutu bağımsız değişkeniyle belirtme ihtiyacını ortadan) ve bunlar otomatik olarak yeni, güvenli dekiler ile daha eski, güvenli olmayan işlevleri değiştirebilirsiniz. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**mbstowcs_s**|\<stdlib.h >|
|**_mbstowcs_s_l**|\<stdlib.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
