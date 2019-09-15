---
title: mbsrtowcs_s
ms.date: 11/04/2016
api_name:
- mbsrtowcs_s
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
- api-ms-win-crt-convert-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- mbsrtowcs_s
helpviewer_keywords:
- mbsrtowcs_s function
ms.assetid: 4ee084ec-b15d-4e5a-921d-6584ec3b5a60
ms.openlocfilehash: d79cceaf923c1da126a1d133a8d2eb8752883457
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70952095"
---
# <a name="mbsrtowcs_s"></a>mbsrtowcs_s

Geçerli yerel ayarda çok baytlı bir karakter dizesini, geniş karakter dizesi gösterimine dönüştürür. [CRT 'Deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklanan şekilde, güvenlik geliştirmeleriyle [mbsrtowcs](mbsrtowcs.md) sürümü.

## <a name="syntax"></a>Sözdizimi

```C
errno_t mbsrtowcs_s(
   size_t * pReturnValue,
   wchar_t * wcstr,
   size_t sizeInWords,
   const char ** mbstr,
   size_t count,
   mbstate_t * mbstate
);
template <size_t size>
errno_t mbsrtowcs_s(
   size_t * pReturnValue,
   wchar_t (&wcstr)[size],
   const char ** mbstr,
   size_t count,
   mbstate_t * mbstate
); // C++ only
```

### <a name="parameters"></a>Parametreler

*Ön kapatma değeri*<br/>
Dönüştürülen karakterlerin sayısı.

*wcstr*<br/>
Elde edilen dönüştürülmüş geniş karakter dizesini depolamak için arabelleğin adresi.

*sizeInWords*<br/>
Sözcükteki *wcstr* boyutu (geniş karakterler).

*mbstr*<br/>
Dönüştürülecek çok baytlı karakter dizesinin konumunun dolaylı işaretçisi.

*biriktirme*<br/>
*Wcstr* arabelleğinde depolanacak, Sonlandırıcı null veya [_TRUNCATE](../../c-runtime-library/truncate.md)dahil olmayan en fazla geniş karakter sayısı.

*mbstate*<br/>
**Mbstate_t** dönüştürme durumu nesnesine yönelik bir işaretçi. Bu değer null bir işaretçisiyse, statik bir iç dönüştürme durumu nesnesi kullanılır. İç **mbstate_t** nesnesi iş parçacığı açısından güvenli olmadığından, her zaman kendi *mbstate* parametresini geçirmeniz önerilir.

## <a name="return-value"></a>Dönüş Değeri

Dönüştürme başarılı olursa sıfır veya hata durumunda hata kodu.

|Hata koşulu|Dönüş değeri ve **errno**|
|---------------------|------------------------------|
|*wcstr* boş bir Işaretçi ve *sizeınwords* > 0|**EINVAL**|
|*mbstr* null bir işaretçisidir|**EINVAL**|
|*Mbstr* tarafından dolaylı olarak işaret edilen dize, geçerli yerel ayar için geçerli olmayan çok baytlı bir sıra içeriyor.|**EILSEQ**|
|Hedef arabellek dönüştürülmüş dizeyi ( *Count* **_TRUNCATE**olmadığı müddetçe) çok küçük. daha fazla bilgi için bkz. açıklamalar|**ERANGE**|

Bu koşullardan herhangi biri oluşursa, geçersiz parametre özel durumu [parametre doğrulamada](../../c-runtime-library/parameter-validation.md) açıklandığı şekilde çağrılır. Yürütmenin devam etmesine izin veriliyorsa, işlev bir hata kodu döndürür ve tabloda belirtilen **errno** değerini ayarlar.

## <a name="remarks"></a>Açıklamalar

**Mbsrtowcs_s** işlevi, *mbstr* tarafından işaret edilen arabellekte depolanan bir çok baytlı karakter *dizesini,* *mbstate*tarafından işaret edilen arabellekte bulunan geniş karakterlere dönüştürür. Bu koşullardan biri karşılanana kadar dönüştürme her karakter için devam eder:

- Çok baytlı null karakter ile karşılaşıldı

- Geçersiz çok baytlı bir karakter ile karşılaşıldı

- *Wcstr* arabelleğinde depolanan geniş karakterlerin sayısı eşittir *Count*.

Wcstr null işaretçisiyse, *wcstr* hedef dizesi her zaman bir hata durumunda bile null olarak sonlandırılır.

*Count* özel değeri [_TRUNCATE](../../c-runtime-library/truncate.md)ise, **mbsrtowcs_s** , dizenin büyük bir kısmını hedef arabelleğe sığdıracak şekilde dönüştürür, ancak yine de bir null Sonlandırıcı için oda bırakır.

**Mbsrtowcs_s** , kaynak dizeyi başarıyla dönüştürdüğünde, boyutu dönüştürülmüş dizenin geniş karakterlere ve null sonlandırıcısının  *&#42;ön yük değerine*koyar, ancak *pReturnValue* bir null işaretçi değildir. Bu, *wcstr* bağımsız değişkeni null işaretçisiyse ve gerekli arabellek boyutunu belirlemenize izin verseler de gerçekleşir. *Wcstr* null işaretçisiyse, *sayı* yoksayılıp sayılmadığını unutmayın.

*Wcstr* null bir işaretçi değilse, bir Sonlandırıcı null karaktere ulaşıldığından, *mbstr* tarafından işaret edilen işaretçi nesnesine, dönüştürme durdurulmuşsa null işaretçi atanır. Aksi takdirde, adres, varsa, yalnızca son çok baytlı karakteri geçmiş olan adrese atanır. Bu, bir sonraki işlev çağrısının, bu çağrının durdurulduğu yerde dönüştürmeyi yeniden başlatmasını sağlar.

*Mbstate* null işaretçisiyse, Library Internal **mbstate_t** dönüştürme durumu statik nesnesi kullanılır. Bu iç statik nesne iş parçacığı açısından güvenli olmadığından, kendi *mbstate* değerini geçirmeniz önerilir.

**Mbsrtowcs_s** , geçerli yerel ayarda geçerli olmayan bir çok baytlı karakterle karşılaşırsa,  *&#42;ön*1 ' i önceden yapılan değere koyar, hedef arabellek *wcstr* değerini boş bir dizeye ayarlar, **errno** 'u **eilseq**olarak ayarlar ve döndürür **Eilseq**.

*Mbstr* ve *wcstr* tarafından işaret edilen sıralar çakışırsa, **mbsrtowcs_s** davranışı tanımsızdır. **mbsrtowcs_s** , geçerli yerel ayarın LC_TYPE kategorisinden etkilenir.

> [!IMPORTANT]
> *Wcstr* ve *mbstr* 'in çakışmadığından ve bu *sayının* dönüştürülecek çok baytlı karakterlerin sayısını doğru yansıttığından emin olun.

**Mbsrtowcs_s** işlevi, [mbstowcs_s, _mbstowcs_s_l](mbstowcs-s-mbstowcs-s-l.md) öğesinden yeniden startability 'e göre farklılık gösterir. Dönüştürme durumu, aynı veya diğer yeniden başlatılabilir işlevlere sonraki çağrılar için *mbstate* 'de depolanır. Yeniden başlatılabilir ve yeniden başlatılabilir işlevlerin kullanımı karıştırılması halinde sonuçlar tanımsızdır. Örneğin, **mbstowcs_s**yerine **mbsrtowcs_s** için sonraki bir çağrı kullanılırsa, bir uygulamanın **mbslen**yerine **mbsrlen** kullanması gerekir.

' C++De, bu işlevin kullanılması şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir (bir boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırır) ve daha yeni ve güvenli, güvenli karşılıklarını kullanarak otomatik olarak eski, güvenli olmayan işlevleri değiştirebilir. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

## <a name="exceptions"></a>Özel Durumlar

Geçerli iş parçacığında hiçbir işlev bu işlev yürütüldüğü ve *mbstate* bağımsız değişkeni null bir işaretçi **olmadığı sürece** **mbsrtowcs_s** işlevi çoklu iş parçacığı güvenlidir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**mbsrtowcs_s**|\<wchar. h >|

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbrtowc](mbrtowc.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[mbstowcs_s, _mbstowcs_s_l](mbstowcs-s-mbstowcs-s-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
