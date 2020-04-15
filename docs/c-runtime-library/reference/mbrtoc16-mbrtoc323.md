---
title: mbrtoc16, mbrtoc323
ms.date: 4/2/2020
api_name:
- mbrtoc16
- mbrtoc32
- _o_mbrtoc16
- _o_mbrtoc32
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
- mbrtoc16
- mbrtoc32
- uchar/mbrtoc16
- uchar/mbrtoc32
helpviewer_keywords:
- mbrtoc16 function
- mbrtoc32 function
ms.assetid: 099ade4d-56f7-4e61-8b45-493f1d7a64bd
ms.openlocfilehash: 91755d19eacf73f19700eed7fffbffc529d4e235
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81340974"
---
# <a name="mbrtoc16-mbrtoc32"></a>mbrtoc16, mbrtoc32

Bir dizedeki ilk UTF-8 çok bayt karakterini eşdeğer UTF-16 veya UTF-32 karakterine çevirir.

## <a name="syntax"></a>Sözdizimi

```C
size_t mbrtoc16(
   char16_t* destination,
   const char* source,
   size_t max_bytes,
   mbstate_t* state
);

size_t mbrtoc32(
   char32_t* destination,
   const char* source,
   size_t max_bytes,
   mbstate_t* state
);
```

### <a name="parameters"></a>Parametreler

*Hedef*\
Dönüştürmek için UTF-8 çok bayt karakterinin **char16_t** veya **char32_t** eşdeğerini işaretle. Null ise, işlev bir değer depolamaz.

*Kaynak*\
Dönüştürmek için UTF-8 multibayt karakter dizesini işaretet.

*max_bytes*\
Bir karakterin dönüştürülmesi için incelenebilmek için *kaynaktaki* maksimum bayt sayısı. Bu bağımsız değişken, *kaynakta*kalan herhangi bir null terminator da dahil olmak üzere bir ve bayt sayısı arasında bir değer olmalıdır.

*Durum*\
UTF-8 çok bayt dizesini bir veya daha fazla çıktı karakteriyle yorumlamak için kullanılan **mbstate_t** dönüştürme durumu nesnesine işaretçi.

## <a name="return-value"></a>Döndürülen değer

Başarıda, geçerli *durum* değeri göz önüne alındığında, geçerli olan bu koşullardan ilkinin değerini döndürür:

|Değer|Koşul|
|-----------|---------------|
|0|*Kaynaktan* dönüştürülen sonraki *max_bytes* veya daha az karakter, *hedef* null değilse depolanan değer olan null geniş karaktere karşılık gelir.<br /><br /> *durum* ilk kaydırma durumunu içerir.|
|1 ile *max_bytes*arasında , dahil|Döndürülen değer, geçerli bir çok bayt karakterini tamamlayan *kaynak* baytlarının sayısıdır. Dönüştürülen geniş *karakter, hedef* null değilse depolanır.|
|-3|Önceki bir işlev çağrısından kaynaklanan bir sonraki geniş karakter, *hedef* geçersiz değilse *hedefte* depolanır. Bu çağrı işlevine *kaynaktan* gelen baytlar tüketilmez.<br /><br /> *Kaynak,* temsil etmesi gereken birden fazla geniş karakter gerektiren UTF-8 çok bayt lı bir karaktere işaret ettiğinde (örneğin, bir vekil çifti), bir sonraki işlev çağrısının ek karakteri yazması için *durum* değeri güncelleştirilir.|
|-2|Sonraki *max_bytes* bayt eksik, ancak potansiyel olarak geçerli, UTF-8 çok bayt karakterini temsil eder. *Hedefte*hiçbir değer depolanır. *max_bytes* sıfırsa bu sonuç oluşabilir.|
|-1|Bir kodlama hatası oluştu. Sonraki *max_bytes* veya daha az bayt tam ve geçerli bir UTF-8 çok bayt karakterine katkıda bulunmaz. *Hedefte*hiçbir değer depolanır.<br /><br /> **EILSEQ** **errno'da** depolanır ve dönüşüm durumu değeri *durumu* belirtilmemiştir.|

## <a name="remarks"></a>Açıklamalar

**Mbrtoc16** işlevi, ilk tam, geçerli UTF-8 çok bayt karakterini bulmak için *kaynaktan* *max_bytes* bayt kadar okur ve ardından eşdeğer UTF-16 karakterini *hedefte*depolar. Karakter, bir vekil çifti gibi birden fazla UTF-16 çıkış karakteri gerektiriyorsa, *durum* değeri sonraki UTF-16 karakterini **mbrtoc16'ya**bir sonraki çağrıda *hedefte* depolamak üzere ayarlanır. **Mbrtoc32** işlevi aynıdır, ancak çıktı UTF-32 karakteri olarak depolanır.

*Kaynak* null ise, bu işlevler *hedef*için `""` **NULL** bağımsız değişkenleri kullanılarak yapılan bir çağrının eşdeğerini döndürdü , *(kaynak*için boş, null-terminatedstring) ve *max_bytes*için 1 . *Hedef* ve *max_bytes* geçirilen değerleri yoksayılır.

*Kaynak* null değilse, işlev dize başında başlar ve herhangi bir vardiya dizileri de dahil olmak üzere bir sonraki UTF-8 çok bayt karakteri tamamlamak için gerekli bayt sayısını belirlemek için *max_bytes* bayt kadar denetler. İncelenen baytlar geçerli ve eksiksiz bir UTF-8 çok bayt karakteri içeriyorsa, işlev karakteri eşdeğer 16 bit veya 32 bit geniş karakter veya karaktere dönüştürür. *Hedef* null değilse, işlev hedefteki ilk (ve büyük olasılıkla yalnızca) sonuç karakterini depolar. Ek çıktı karakterleri gerekiyorsa, bir değer *durum*olarak ayarlanır , böylece sonraki işlev çağrıları ek karakterler çıktı ve değeri -3 döndürün. Başka çıktı karakteri gerekli değilse, *durum* ilk kaydırma durumuna ayarlanır.

UTF-8 olmayan multibayt karakterleri UTF-16 LE karakterlere dönüştürmek için [mbrtowc, mbtowc](mbrtowc.md) [veya _mbtowc_l](mbtowc-mbtowc-l.md) işlevlerini kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgi|C++ üstbilgi|
|--------------|--------------|------------------|
|**mbrtoc16**, **mbrtoc32**|\<uchar.h>|\<cuchar>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Veri dönüştürme](../data-conversion.md)\
[Yerel ayar](../locale.md)\
[Çok bayt karakter dizilerinin yorumlanması](../interpretation-of-multibyte-character-sequences.md)\
[c16rtomb, c32rtomb](c16rtomb-c32rtomb1.md)\
[mbrtowc](mbrtowc.md)\
[mbsrtowcs](mbsrtowcs.md)\
[mbsrtowcs_s](mbsrtowcs-s.md)
