---
title: mbrtoc16, mbrtoc323
ms.date: 11/04/2016
api_name:
- mbrtoc16
- mbrtoc32
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
- mbrtoc16
- mbrtoc32
- uchar/mbrtoc16
- uchar/mbrtoc32
helpviewer_keywords:
- mbrtoc16 function
- mbrtoc32 function
ms.assetid: 099ade4d-56f7-4e61-8b45-493f1d7a64bd
ms.openlocfilehash: 52bcec5911fdc2ecbb073ae0042777aa4eb2b963
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70952432"
---
# <a name="mbrtoc16-mbrtoc32"></a>mbrtoc16, mbrtoc32

Dar dizedeki ilk çok baytlı karakteri eşdeğer UTF-16 veya UTF-32 karakteriyle çevirir.

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

*hedefine*<br/>
Dönüştürülecek çok baytlı karakterin **char16_t** veya **char32_t** eşdeğerini işaretçisi. Null ise, işlev bir değer depolamaz.

*source*<br/>
Dönüştürülecek çok baytlı karakter dizesinin işaretçisi.

*max_bytes*<br/>
Dönüştürülecek karakteri incelemek için *kaynaktaki* en fazla bayt sayısı. Bu, *kaynak*içinde kalan herhangi bir null Sonlandırıcı dahil olmak üzere bir ve bayt sayısı arasında bir değer olmalıdır.

*durumunda*<br/>
Çok baytlı dizeyi bir veya daha fazla çıkış karakteriyle yorumlamak için kullanılan bir **mbstate_t** dönüştürme durumu nesnesine yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda, geçerli *durum* değeri verildiğinde geçerli olan bu koşulların ilk değerini döndürür:

|Değer|Koşul|
|-----------|---------------|
|0|*Kaynaktan* dönüştürülen sonraki *max_bytes* veya daha az karakter, *hedef* null değilse depolanan değer olan null geniş karaktere karşılık gelir.<br /><br /> *durum* , ilk kaydırma durumunu içerir.|
|Dahil olmak üzere 1 ile *max_bytes*arasında|Döndürülen değer, geçerli bir çok baytlı karakteri tamamlayacak *kaynak* bayt sayısıdır. *Hedef* null değilse, dönüştürülen geniş karakter saklanır.|
|-3|*Hedef* null değilse, işleve yapılan önceki çağrıdan kaynaklanan bir sonraki geniş karakter *hedefte* depolandı. Bu işleve yapılan bu çağrı tarafından *kaynaktan* hiçbir bayt tüketilmemiş.<br /><br /> *Kaynak* , birden fazla geniş karakter (örneğin, bir vekil çifti) temsil etmesi gereken çok baytlı bir karakteri işaret ediyorsa, sonraki işlev çağrısının ek karakteri yazması için *durum* değeri güncellenir.|
|-2|Sonraki *max_bytes* baytları tamamlanmamış, ancak potansiyel olarak geçerli çok baytlı bir karakteri temsil eder. *Hedefte*hiçbir değer depolanmaz. Bu sonuç, *max_bytes* sıfır olduğunda meydana gelebilir.|
|-1|Bir kodlama hatası oluştu. Sonraki *max_bytes* veya daha az bayt, bir bütün ve geçerli çok baytlı karaktere katkıda bulunamaz. *Hedefte*hiçbir değer depolanmaz.<br /><br /> **Eilseq** , **errno** 'da depolanır ve dönüştürme durumunun *durumu* belirtilmemiş olur.|

## <a name="remarks"></a>Açıklamalar

**Mbrtoc16** işlevi, ilk tamamlanan, geçerli çok baytlı karakteri bulmak için *kaynaktan* en fazla *max_bytes* bayt okur ve sonra karşılık gelen UTF-16 karakterini *hedefte*depolar. Kaynak baytlar, geçerli iş parçacığı çok baytlı yerel ayarına göre yorumlanır. Çok baytlı karakter, vekil çifti gibi birden fazla UTF-16 çıkış karakteri gerektiriyorsa, *durum* değeri sonraki **mbrtoc16**çağrısında bir sonraki UTF-16 karakterini *hedefte* depolayacak şekilde ayarlanır. **Mbrtoc32** işlevi aynıdır, ancak ÇıKTı bir UTF-32 karakteri olarak depolanır.

*Kaynak* null ise, bu işlevler *hedef*için **null** bağımsız değişkenler kullanılarak oluşturulan çağrının eşdeğerini döndürür, *kaynak*için **""** ve *max_bytes*için 1. Geçirilen *hedef* ve *max_bytes* değerleri yok sayılır.

*Kaynak* null değilse, işlev dizenin başlangıcında başlar ve kaydırma dizileri dahil olmak üzere bir sonraki çok baytlı karakteri tamamlamaya yönelik gereken bayt sayısını belirlemede *max_bytes* bayta kadar inceler. İncelenen baytlar geçerli ve tam bir çok baytlı karakter içeriyorsa, işlev karakteri 16 bit veya 32 bitlik geniş karakter veya karakterlere dönüştürür. *Hedef* null değilse, işlev hedefteki ilk (ve muhtemelen yalnızca) sonuç karakterini depolar. Ek çıkış karakterleri gerekliyse, bir değer bir *durum*olarak ayarlanır, böylece işlevin sonraki çağrıları ek karakterlerin çıktısını verir ve-3 değerini döndürür. Daha fazla çıkış karakteri gerekmiyorsa, *durum* ilk kaydırma durumuna ayarlanır.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++üst bilgi|
|--------------|--------------|------------------|
|**mbrtoc16**, **mbrtoc32**|\<uşar. h >|\<cuchar >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[c16rtomb, c32rtomb](c16rtomb-c32rtomb1.md)<br/>
[mbrtowc](mbrtowc.md)<br/>
[mbsrtowcs](mbsrtowcs.md)<br/>
[mbsrtowcs_s](mbsrtowcs-s.md)<br/>
