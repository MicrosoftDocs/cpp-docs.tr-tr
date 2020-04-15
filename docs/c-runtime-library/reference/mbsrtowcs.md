---
title: mbsrtowcs
ms.date: 4/2/2020
api_name:
- mbsrtowcs
- _o_mbsrtowcs
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
- mbsrtowcs
helpviewer_keywords:
- mbsrtowcs function
ms.assetid: f3a29de8-e36e-425b-a7fa-a258e6d7909d
ms.openlocfilehash: 509046e1c55d89cd78b09076838983691423a1ee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338891"
---
# <a name="mbsrtowcs"></a>mbsrtowcs

Geçerli yerel ayardaki çok bayt karakter dizesini, çok baytlı bir karakterin ortasında yeniden başlatma özelliğiyle karşılık gelen geniş karakter dizesine dönüştürür. Bu işlevin daha güvenli bir sürümü mevcuttur; [mbsrtowcs_s](mbsrtowcs-s.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
size_t mbsrtowcs(
   wchar_t *wcstr,
   const char **mbstr,
   sizeof count,
   mbstate_t *mbstate
);
template <size_t size>
size_t mbsrtowcs(
   wchar_t (&wcstr)[size],
   const char **mbstr,
   sizeof count,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>Parametreler

*Wcstr*<br/>
Dönüştürülmüş geniş karakter dizesini depolamak için adres.

*mbstr*<br/>
Dönüştürmek için çok bayt karakter dizesinin konumuna dolaylı işaretçi.

*Sayısı*<br/>
Wcstr'de dönüştürmek ve depolamak için maksimum karakter *wcstr*sayısı (bayt değil).

*mbstate*<br/>
**mbstate_t** dönüştürme durumu nesnesine işaretçi. Bu değer null işaretçisi ise, statik bir iç dönüşüm durumu nesnesi kullanılır. İç **mbstate_t** nesnesi iş parçacığı için güvenli olmadığından, her zaman kendi *mbstate* parametrenizi geçirmenizi öneririz.

## <a name="return-value"></a>Dönüş Değeri

Varsa sonlandırıcı null karakteri dahil değil, başarıyla dönüştürülen karakter sayısını verir. Bir hata oluştuysa (size_t)(-1) döndürür ve eilseq'e **errno** ayarlar.

## <a name="remarks"></a>Açıklamalar

**Mbsrtowcs** işlevi dolaylı olarak *mbstr*tarafından işaret multibayt karakter bir dize dönüştürür , *wcstr*tarafından işaret edilen arabelleksaklanan geniş karakterler , *mbstate*bulunan dönüşüm durumu kullanarak . Dönüştürme, sonlandırıcı bir null multibayt karakteriyle karşılaşılınceye, geçerli yerel ayardaki geçerli bir karaktere karşılık gelen çok baytlı bir diziyle karşılaşına veya *sayım* karakterleri dönüştürülene kadar her karakter için devam eder. **Mbsrtowcs** çok bayt null karakteriyle ('\0') *sayım* gerçekleşmeden önce veya ne zaman gerçekleşirse, onu 16 bitlik bir sonlandırıcı null karaktere dönüştürür ve durur.

Böylece, *wcstr'deki* geniş karakter dizesi, yalnızca **mbsrtowcs** dönüştürme sırasında çok baytlı null karakterle karşılaşırsa geçersiz kılınır. *Mbstr* ve *wcstr* ile işaret edilen diziler çakışıyorsa, **mbsrtowcs'nin** davranışı tanımsızdır. **mbsrtowcs** geçerli yerel LC_TYPE kategorisinden etkilenir.

**Mbsrtowcs** fonksiyonu [mbstowcs farklıdır, _mbstowcs_l](mbstowcs-mbstowcs-l.md) yeniden başlatılabilirlik. Dönüştürme durumu, aynı veya diğer yeniden başlatılabilir işlevlere sonraki çağrılar için *mbstate'te* depolanır. Yeniden başlatılabilir ve yeniden başlatılamaz işlevlerin kullanımı karıştırılırken sonuçlar tanımsızdır.  Örneğin, **mbsrtowcs yerine mbsrtowcs** sonraki bir çağrı kullanılırsa, bir **mbstowcs**uygulama **mbsrlen**yerine **mbsrlen** kullanmalıdır.

*Wcstr* null işaretçi değilse, sonlandırıcı null karaktere ulaşıldığından dönüştürme durduysa *mbstr* tarafından işaret edilen işaretçi nesnesine bir null işaretçi atanır. Aksi takdirde, varsa dönüştürülen son çok bayt karakterinin hemen yanından adresa atanır. Bu, sonraki bir işlev çağrısının bu çağrının durdurulduğu dönüştürmeyi yeniden başlatmasına olanak tanır.

*Wcstr* bağımsız değişkeni null işaretçisi ise, *sayı* bağımsız değişkeni yoksayılır ve **mbsrtowcs** hedef dize için geniş karakterlerde gerekli boyutu döndürür. *Mbstate* null işaretçisi ise, işlev iş parçacığı güvenli olmayan statik **mbstate_t** dönüştürme durumu nesnesi kullanır. Karakter dizisi *mbstr* karşılık gelen bir çok bayt karakter gösterimi yoksa, bir -1 döndürülür ve **errno** **EILSEQ**olarak ayarlanır.

*Mbstr* isa null işaretçisi ise, geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmenin devam etmesine izin verilirse, bu işlev **errno'u** **EINVAL'e** ayarlar ve -1 döndürür.

C++'da bu işlev, bu işlevin daha yeni ve güvenli karşılığını çağıran bir şablon aşırı yüklemesi vardır. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="exceptions"></a>Özel durumlar

**Mbsrtowcs** işlevi, bu işlev yürütülderken ve *mbstate* bağımsız değişkeni null işaretçisi olmadığı sürece, geçerli iş parçacığındaki işlev **setlocale'yi** aradığı sürece çok iş parçacığı güvenlidir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**mbsrtowcs**|\<wchar.h>|

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbrtowc](mbrtowc.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
