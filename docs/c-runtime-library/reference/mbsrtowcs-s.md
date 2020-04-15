---
title: mbsrtowcs_s
ms.date: 4/2/2020
api_name:
- mbsrtowcs_s
- _o_mbsrtowcs_s
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- mbsrtowcs_s
helpviewer_keywords:
- mbsrtowcs_s function
ms.assetid: 4ee084ec-b15d-4e5a-921d-6584ec3b5a60
ms.openlocfilehash: 62ae534e8080b74ada49cca005811a049055cb65
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338894"
---
# <a name="mbsrtowcs_s"></a>mbsrtowcs_s

Geçerli yerel ayardaki çok bayt karakter dizesini geniş karakter dize gösterimine dönüştürün. [CRT Güvenlik Özellikleri](../../c-runtime-library/security-features-in-the-crt.md)açıklandığı gibi güvenlik geliştirmeleri ile [mbsrtowcs](mbsrtowcs.md) bir sürümü.

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
Dönüştürülen karakter sayısı.

*Wcstr*<br/>
Dönüştürülen geniş karakter dizesini depolamak için arabelleğin adresi.

*sizeInWords*<br/>
Kelimelerde *wcstr* boyutu (geniş karakterler).

*mbstr*<br/>
Dönüştürülecek çok bayt karakter dizesinin konumuna dolaylı işaretçi.

*Sayısı*<br/>
Null veya [_TRUNCATE](../../c-runtime-library/truncate.md)sonlandırma dahil değil, *wcstr* arabellekte depolanması için geniş karakter maksimum sayısı.

*mbstate*<br/>
**mbstate_t** dönüştürme durumu nesnesine işaretçi. Bu değer null işaretçisi ise, statik bir iç dönüşüm durumu nesnesi kullanılır. İç **mbstate_t** nesnesi iş parçacığı için güvenli olmadığından, her zaman kendi *mbstate* parametrenizi geçirmenizi öneririz.

## <a name="return-value"></a>Dönüş Değeri

Dönüştürme başarılı olursa sıfır veya hata yla ilgili bir hata kodu.

|Hata koşulu|İade değeri ve **errno**|
|---------------------|------------------------------|
|*wcstr* bir null işaretçi ve *sizeInWords* > 0|**Eınval**|
|*mbstr* bir null işaretçi|**Eınval**|
|Mbstr tarafından dolaylı *mbstr* olarak işaret edilen dize, geçerli yerel bölge için geçerli olmayan çok baytlı bir dizi içerir.|**Eılseq**|
|Hedef arabellek dönüştürülen dizeyi içermeyecek kadar küçüktür *(sayım* **_TRUNCATE**sürece ; daha fazla bilgi için Açıklamalar'a bakın)|**Erange**|

Bu koşullardan herhangi biri oluşursa, geçersiz parametre özel durumu [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md) açıklandığı gibi çağrılır. Yürütmenin devam etmesine izin verilirse, işlev bir hata kodu döndürür ve tabloda belirtildiği gibi **errno** ayarlar.

## <a name="remarks"></a>Açıklamalar

**mbsrtowcs_s** işlevi, *mbstate'te* bulunan dönüşüm durumunu kullanarak, *mbstr*tarafından işaret edilen arabellekte depolanan geniş karakterlere dolaylı olarak işaret edilen çok bayt karakter dizesini *dönüştürür.* Dönüştürme, bu koşullardan biri karşılanana kadar her karakter için devam edecektir:

- Çok baytlı null karakterle karşılaşılır

- Geçersiz bir çok bayt karakteriyle karşılaşılır

- *Wcstr* arabelleğinde depolanan geniş karakter sayısı *eşittir sayısı.*

Hedef dize *wcstr* her zaman null-sonlandırılır, bir hata durumunda bile, *wcstr* null bir işaretçi olmadığı sürece.

*Sayım* [_TRUNCATE](../../c-runtime-library/truncate.md)özel bir değerse, **mbsrtowcs_s,** null terminator için yer bırakırken, hedef arabelleğe sığacak kadar dize dönüştürür.

**mbsrtowcs_s** kaynak dizesini başarıyla dönüştürürse, boyutu dönüştürülmüş dizenin geniş karakterlerine ve null sonlandırıcıyı *&#42;pReturnValue'a*koyar, *pReturnValue'un* null işaretçisi olmaması koşuluyla. Bu, *wcstr* bağımsız değişkeni null işaretçi olsa bile oluşur ve gerekli arabellek boyutunu belirlemenize olanak tanır. *WCSTR* null işaretçisi ise, *sayım* yoksayılır.

*Wcstr* null işaretçi değilse, sonlandırıcı null karaktere ulaşıldığından dönüştürme durduysa *mbstr* tarafından işaret edilen işaretçi nesnesine bir null işaretçi atanır. Aksi takdirde, varsa dönüştürülen son çok bayt karakterinin hemen yanından adresa atanır. Bu, sonraki bir işlev çağrısının bu çağrının durdurulduğu dönüştürmeyi yeniden başlatmasına olanak tanır.

*Mbstate* null işaretçisi ise, kitaplık iç **mbstate_t** dönüştürme durumu statik nesne kullanılır. Bu iç statik nesne iş parçacığı güvenli olmadığından, kendi *mbstate* değeri geçmenizi öneririz.

**mbsrtowcs_s** geçerli yerel olarak geçerli olmayan bir çok bayt karakter le karşılaşırsa, *&#42;pReturnValue'de*-1 koyar, hedef arabellek *wcstr'i* boş bir dize ayarlar, **Errno'yu** **EILSEQ'a**ayarlar ve **EILSEQ'yu**döndürür.

*Mbstr* ve *wcstr* ile işaret edilen diziler çakışıyorsa, **mbsrtowcs_s** davranışı tanımsızdır. **mbsrtowcs_s** geçerli yerel LC_TYPE kategorisinden etkilenir.

> [!IMPORTANT]
> Wcstr ve *mbstr'nin* çakışmadığından ve bu *wcstr* *sayımda* dönüştürülecek çok bayt karakter sayısını doğru şekilde yansıttığından emin olun.

**mbsrtowcs_s** işlevi [mbstowcs_s](mbstowcs-s-mbstowcs-s-l.md) _mbstowcs_s_l yeniden başlatılabilirliği ile farklıdır. Dönüştürme durumu, aynı veya diğer yeniden başlatılabilir işlevlere sonraki çağrılar için *mbstate'te* depolanır. Yeniden başlatılabilir ve yeniden başlatılamaz işlevlerin kullanımı karıştırılırken sonuçlar tanımsızdır. Örneğin, bir uygulama **mbslen**yerine **mbsrlen** kullanmalıdır , **mbsrtowcs_s** sonraki bir çağrı **mbstowcs_s**yerine kullanılırsa.

C++'da, bu işlevi kullanmak şablon aşırı yüklemeleri ile basitleştirilir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkartabilir (boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırabilir) ve daha yeni, güvenli karşılıklarını kullanarak eski, güvenli olmayan işlevleri otomatik olarak değiştirebilirler. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="exceptions"></a>Özel durumlar

Bu işlev yürütülderken ve *mbstate* bağımsız değişkeni null işaretçi sayılsa da, geçerli iş parçacığındaki işlev **setlocale'yi** çağırmazsa **mbsrtowcs_s** işlevi çok iş parçacığı güvenlidir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**mbsrtowcs_s**|\<wchar.h>|

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbrtowc](mbrtowc.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[mbstowcs_s, _mbstowcs_s_l](mbstowcs-s-mbstowcs-s-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
