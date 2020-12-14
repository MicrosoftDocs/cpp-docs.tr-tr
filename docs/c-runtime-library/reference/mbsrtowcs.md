---
description: 'Daha fazla bilgi edinin: mbsrtowcs'
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- mbsrtowcs
helpviewer_keywords:
- mbsrtowcs function
ms.assetid: f3a29de8-e36e-425b-a7fa-a258e6d7909d
ms.openlocfilehash: 83979058e33ffc3874f26cb8ef70f888195e6644
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97240188"
---
# <a name="mbsrtowcs"></a>mbsrtowcs

Geçerli yerel ayarda bulunan çok baytlı bir karakter dizesini, bir çok baytlı karakterin ortasında yeniden başlatma özelliği ile birlikte karşılık gelen geniş karakter dizesine dönüştürür. Bu işlevin daha güvenli bir sürümü kullanılabilir; bkz. [mbsrtowcs_s](mbsrtowcs-s.md).

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

*wcstr*<br/>
Elde edilen dönüştürülmüş geniş karakter dizesinin depolandığı adres.

*mbstr*<br/>
Dönüştürülecek çok baytlı karakter dizesinin konumuna dolaylı işaretçi.

*biriktirme*<br/>
*Wcstr* içinde dönüştürülecek ve depolanacak en fazla karakter sayısı (bayt değil).

*mbstate*<br/>
**Mbstate_t** dönüştürme durumu nesnesine yönelik bir işaretçi. Bu değer null bir işaretçisiyse, statik bir iç dönüştürme durumu nesnesi kullanılır. İç **mbstate_t** nesnesi iş parçacığı açısından güvenli olmadığından, her zaman kendi *mbstate* parametresini geçirmeniz önerilir.

## <a name="return-value"></a>Dönüş Değeri

Varsa, Sonlandırıcı null karakteri dahil değil, başarıyla dönüştürülen karakter sayısını döndürür. Bir hata oluştuysa (size_t) (-1) döndürür ve **errno** 'u EILSEQ olarak ayarlar.

## <a name="remarks"></a>Açıklamalar

**Mbsrtowcs** işlevi, *mbstr*'e dolaylı olarak işaret edilen bir çok baytlı karakter dizesini, *mbstate* içinde bulunan dönüştürme durumu kullanılarak *wcstr* tarafından işaret edilen arabellekte depolanan geniş karakterlere dönüştürür. Dönüştürme, bir Sonlandırıcı null çok baytlı karakteriyle karşılaşıldığında her karakter için devam eder, geçerli yerel ayarda geçerli bir karaktere karşılık gelmeyen çok baytlı bir diziye rastlandı veya *sayma* karakterleri dönüştürülmüyor. **Mbsrtowcs** çok baytlı null karakterle (' \ 0 ') karşılaşırsa veya *sayı* gerçekleştiğinde, bu değeri 16 bit bir Sonlandırıcı null karaktere dönüştürür ve duraklar.

Bu nedenle, *wcstr* konumundaki geniş karakter dizesi yalnızca **mbsrtowcs** dönüştürme sırasında çok baytlı bir null karakterle karşılaştığında null olarak sonlandırılır. *Mbstr* ve *wcstr* tarafından işaret edilen sıralar çakışırsa, **mbsrtowcs** davranışı tanımsızdır. **mbsrtowcs** , geçerli yerel ayarın LC_TYPE kategorisinden etkilenir.

**Mbsrtowcs** işlevi [mbstowcs öğesinden farklı _mbstowcs_l,](mbstowcs-mbstowcs-l.md) yeniden başlangıçlarından farklıdır. Dönüştürme durumu, aynı veya diğer yeniden başlatılabilir işlevlere sonraki çağrılar için *mbstate* 'de depolanır. Yeniden başlatılabilir ve yeniden başlatılabilir işlevlerin kullanımı karıştırılması halinde sonuçlar tanımsızdır.  Örneğin, bir uygulama **mbslen** yerine **mbsrlen** değerini kullanmalıdır. Bu, sonraki bir **mbsrtowcs** çağrısı için **mbstowcs** yerine kullanılır.

*Wcstr* null bir işaretçi değilse, bir Sonlandırıcı null karaktere ulaşıldığından, *mbstr* tarafından işaret edilen işaretçi nesnesine, dönüştürme durdurulmuşsa null işaretçi atanır. Aksi takdirde, adres, varsa, yalnızca son çok baytlı karakteri geçmiş olan adrese atanır. Bu, bir sonraki işlev çağrısının, bu çağrının durdurulduğu yerde dönüştürmeyi yeniden başlatmasını sağlar.

*Wcstr* bağımsız değişkeni null bir işaretçisiyse, *Count* bağımsız değişkeni yok sayılır ve **mbsrtowcs** , hedef dize için gereken boyutu geniş karakterler halinde döndürür. *Mbstate* null işaretçisiyse, işlev iş parçacığı güvenli olmayan bir statik dahili **mbstate_t** dönüştürme durumu nesnesi kullanır. *Mbstr* karakter dizisi karşılık gelen bir çok baytlı karakter gösterimine sahip değilse,-1 döndürülür ve **errno** , **eilseq** olarak ayarlanır.

*Mbstr* ISA null Işaretçisiyse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev **errno** ' ı **EINVAL** olarak ayarlar ve-1 döndürür.

C++ ' da bu işlevin, bu işlevin daha yeni ve güvenli karşılığı sağlayan bir şablon aşırı yüklemesi vardır. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="exceptions"></a>Özel durumlar

Geçerli iş parçacığında hiçbir işlev bu işlev yürütüldüğü ve *mbstate* bağımsız değişkeni null bir işaretçi **olmadığı sürece,** **mbsrtowcs** işlevi çoklu iş parçacığı güvenlidir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**mbsrtowcs**|\<wchar.h>|

## <a name="see-also"></a>Ayrıca bkz.

[Veri dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Ayarlar](../../c-runtime-library/locale.md)<br/>
[Multibyte-Character sıralarının yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbrtowc](mbrtowc.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
