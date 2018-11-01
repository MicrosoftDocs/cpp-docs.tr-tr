---
title: mbsrtowcs_s
ms.date: 11/04/2016
apiname:
- mbsrtowcs_s
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
- mbsrtowcs_s
helpviewer_keywords:
- mbsrtowcs_s function
ms.assetid: 4ee084ec-b15d-4e5a-921d-6584ec3b5a60
ms.openlocfilehash: a935b5181078f3b08ba5f2f89c581ed8cce8ded5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50588834"
---
# <a name="mbsrtowcss"></a>mbsrtowcs_s

Çok baytlı karakter dizesi geçerli ayardaki geniş karakter dize gösterimine dönüştürür. Bir sürümünü [mbsrtowcs](mbsrtowcs.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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

*pReturnValue*<br/>
Dönüştürülecek karakter sayısı.

*wcstr*<br/>
Ortaya çıkan depolayan arabellek adresi geniş karakter dizesi dönüştürülür.

*sizeInWords*<br/>
Boyutu *wcstr* sözcüklerin (geniş karakter).

*mbstr*<br/>
Dönüştürülecek çok baytlı karakter dizesi konumunu dolaylı işaretçisi.

*Sayısı*<br/>
Depolamak için geniş karakterlerin sayısı *wcstr* arabellek, sonlandırıcı null içermeden veya [_TRUNCATE](../../c-runtime-library/truncate.md).

*mbstate*<br/>
Bir işaretçi bir **mbstate_t** dönüştürme durum nesnesi. Bu değer bir null işaretçi ise, statik iç dönüştürme durum nesnesi kullanılır. Olduğundan iç **mbstate_t** nesne iş parçacığı güvenli değil, size her zaman kendi geçmesini öneririz *mbstate* parametresi.

## <a name="return-value"></a>Dönüş Değeri

Dönüştürme başarılı olursa sıfır veya bir hata kodu.

|Hata koşulu|Dönüş değeri ve **errno**|
|---------------------|------------------------------|
|*wcstr* null bir işaretçiyse ve *sizeInWords* > 0|**EINVAL**|
|*mbstr* null bir işaretçiyse|**EINVAL**|
|Dize dolaylı olarak tarafından işaret edilen *mbstr* , geçerli yerel ayarı için geçerli olmayan bir çok baytlı dizisi içerir.|**EILSEQ**|
|Hedef arabelleğinin içeren dönüştürülmüş dize çok küçük (sürece *sayısı* olduğu **_TRUNCATE**; daha fazla bilgi için açıklamalara bakın)|**ERANGE**|

Bu koşullardan herhangi biri meydana gelirse, açıklanan şekilde geçersiz parametre özel durumu çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md) . Yürütme devam etmesine izin verilirse işlev bir hata kodu döndürür ve ayarlar **errno** tabloda belirtildiği şekilde.

## <a name="remarks"></a>Açıklamalar

**Mbsrtowcs_s** işlevi dönüştürür bir dolaylı olarak işaret ettiği çok baytlı karakter dizesi *mbstr* tarafından işaret edilen arabellek içinde depolanan geniş karakterlerin içine *wcstr*tarafından içindeki dönüştürme durumu kullanarak *mbstate*. Dönüştürme, her karakter için şu koşullardan biri karşılandığında kadar devam eder:

- Çok baytlı bir null karakteri ile karşılaşıldı

- Geçersiz bir çok baytlı karakter karşılaşıldı

- İçinde depolanan geniş karakterlerin sayısını *wcstr* arabellek eşittir *sayısı*.

Hedef dize *wcstr* null ile sonlandırılmış bir hata olması durumunda bile, her zaman olduğu sürece *wcstr* bir null işaretçidir.

Varsa *sayısı* özel değer [_TRUNCATE](../../c-runtime-library/truncate.md), **mbsrtowcs_s** büyük bir işlem olarak dize dönüştürür yine de bir null yer bırakarak hedef arabellek içine Sığdır Sonlandırıcı.

Varsa **mbsrtowcs_s** başarılı bir şekilde kaynak dizesini dönüştürür dönüştürülmüş dize ve içine null Sonlandırıcı geniş karakter cinsinden boyutu koyar  *&#42;pReturnValue*, sağlanan  *pReturnValue* null bir işaretçi değil. Bu meydana bile *wcstr* bağımsız değişkeni null bir işaretçiyse ve gerekli arabellek boyutunu belirlemenize olanak tanır. Unutmayın *wcstr* null bir işaretçiyse, *sayısı* göz ardı edilir.

Varsa *wcstr* null bir işaretçi değil işaretçi nesnesinin tarafından işaret edilen *mbstr* null bir işaretçi bir sonlandırıcı null karakter üst sınırına ulaşıldığından dönüştürme durdurduysanız atanır. Aksi takdirde, varsa, son çok baytlı karakter dönüştürülür, adresi yalnızca geçmiş atanır. Bu, bir sonraki işlev çağrısı dönüştürme yeniden başlatmak bu çağrı durduğu sağlar.

Varsa *mbstate* bir null işaretçiyse, iç Kitaplığı **mbstate_t** dönüştürme durumu statik nesnesi kullanılır. Bu bir iç statik nesne iş parçacığı açısından güvenli olmadığı için kendi geçmesini öneririz *mbstate* değeri.

Varsa **mbsrtowcs_s** geçerli yerel ayarı geçerli değil. bir çok baytlı karakterin karşılaştığında -1 koyar  *&#42;pReturnValue*, hedef arabelleğinin ayarlar *wcstr* boş bir dize olarak ayarlar **errno** için **EILSEQ**ve döndürür **EILSEQ**.

Dizileri işaret ettiği varsa *mbstr* ve *wcstr* üst üste, davranışını **mbsrtowcs_s** tanımsızdır. **mbsrtowcs_s** geçerli yerel ayarı LC_TYPE kategoriye göre etkilenir.

> [!IMPORTANT]
> Emin *wcstr* ve *mbstr* örtüşmeyen ve *sayısı* doğru şekilde dönüştürmek için çok baytlı karakter sayısını yansıtır.

**Mbsrtowcs_s** işlevi farklıdır [mbstowcs_s, _mbstowcs_s_l](mbstowcs-s-mbstowcs-s-l.md) kendi restartability tarafından. Dönüştürme durumunu depolanan *mbstate* aynı ya da yeniden başlatılabilir diğer işlevlere yapılan sonraki çağrılar için. Yeniden başlatılabilir ve nonrestartable işlevlerin kullanımını kullanırken sonuçlar tanımsızdır. Örneğin, bir uygulamanın kullanması gereken **mbsrlen** yerine **mbslen**sonraki çağrı, **mbsrtowcs_s** yerine kullanılan **mbstowcs_s**.

C++'da, bu işlevi kullanmak şablon aşırı yüklemeleriyle basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir (bir boyut bağımsız değişkeni belirtme gereksinimi ortadan kalkar) ve bunlar otomatik olarak eski ve güvenli olmayan işlevlerle daha yeni ve güvenli karşılıkları kullanarak değiştirir. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

## <a name="exceptions"></a>Özel Durumlar

**Mbsrtowcs_s** işlev, çoklu iş parçacığı güvenli bir işlev, geçerli iş parçacığı çağrı **setlocale** bu işlev yürütülürken sürece ve *mbstate* bağımsız değişkeni null bir işaretçi değil.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**mbsrtowcs_s**|\<wchar.h >|

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbrtowc](mbrtowc.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[mbstowcs_s, _mbstowcs_s_l](mbstowcs-s-mbstowcs-s-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
