---
description: 'Hakkında daha fazla bilgi edinin: mbrtoc16, mbrtoc32'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 4132be867186567b31c9e297e6acb4ada68a66ca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97178621"
---
# <a name="mbrtoc16-mbrtoc32"></a>mbrtoc16, mbrtoc32

Dizedeki ilk UTF-8 çok baytlı karakterini karşılık gelen UTF-16 veya UTF-32 karakterine dönüştürür.

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

*hedefine*\
**`char16_t`** **`char32_t`** Dönüştürülecek UTF-8 çok baytlı karakterin veya eşdeğeri için işaretçi. Null ise, işlev bir değer depolamaz.

*kaynaktaki*\
Dönüştürülecek UTF-8 çok baytlı karakter dizesinin işaretçisi.

*max_bytes*\
Dönüştürülecek karakteri incelemek için *kaynaktaki* en fazla bayt sayısı. Bu bağımsız değişken, *kaynak* içinde kalan herhangi bir null Sonlandırıcı dahil olmak üzere bir ve bayt sayısı arasında bir değer olmalıdır.

*durumunda*\
UTF-8 çok baytlı dizesini bir veya daha fazla çıkış karakteriyle yorumlamak için kullanılan **mbstate_t** dönüştürme durumu nesnesine yönelik işaretçi.

## <a name="return-value"></a>Döndürülen değer

Başarılı olduğunda, geçerli *durum* değeri verildiğinde geçerli olan bu koşulların ilk değerini döndürür:

|Değer|Koşul|
|-----------|---------------|
|0|*Kaynaktan* dönüştürülen sonraki *max_bytes* veya daha az karakter, *hedef* null değilse depolanan değer olan null geniş karaktere karşılık gelir.<br /><br /> *durum* , ilk kaydırma durumunu içerir.|
|1 ile *max_bytes*(dahil) arasında|Döndürülen değer, geçerli bir çok baytlı karakteri tamamlayacak *kaynak* bayt sayısıdır. *Hedef* null değilse, dönüştürülen geniş karakter saklanır.|
|-3|*Hedef* null değilse, işleve yapılan önceki çağrıdan kaynaklanan bir sonraki geniş karakter *hedefte* depolandı. Bu işleve yapılan bu çağrı tarafından *kaynaktan* hiçbir bayt tüketilmemiş.<br /><br /> *Kaynak* , birden fazla geniş karakter temsil etmesi için (örneğin, bir vekil çifti) bir UTF-8 çok baytlı karakteri işaret ediyorsa, sonraki işlev çağrısının ek karakteri yazması için *durum* değeri güncellenir.|
|-2|Sonraki *max_bytes* baytları tamamlanmamış, ancak olasılıkla GEÇERLI bir UTF-8 çok baytlı karakterini temsil eder. *Hedefte* hiçbir değer depolanmaz. Bu sonuç, *max_bytes* sıfır olduğunda meydana gelebilir.|
|-1|Bir kodlama hatası oluştu. Sonraki *max_bytes* veya daha az bayt, tam ve geçerlI bir UTF-8 çok baytlı karaktere katkıda bulunamaz. *Hedefte* hiçbir değer depolanmaz.<br /><br /> **Eilseq** , **errno** 'da depolanır ve dönüştürme *durumu değeri belirtilmemiş* olur.|

## <a name="remarks"></a>Açıklamalar

**Mbrtoc16** işlevi, ilk tamamlanmış ve geçerli UTF-8 çok baytlı karakterini bulmak için *kaynaktan* *max_bytes* bayt okur ve sonra karşılık gelen UTF-16 karakterini *hedefte* depolar. Karakter, yedek çifti gibi birden fazla UTF-16 çıkış karakteri gerektiriyorsa, *durum* değeri, sonraki **mbrtoc16** çağrısında bir sonraki UTF-16 karakterini *hedefte* depolayacak şekilde ayarlanır. **Mbrtoc32** işlevi aynıdır, ancak ÇıKTı bir UTF-32 karakteri olarak depolanır.

*Kaynak* null ise, bu işlevler *hedef* için **null** bağımsız değişkenler `""` (boş, null sonlandırılmış bir dize) ve *max_bytes* için 1 kullanılarak yapılan çağrının eşdeğerini döndürür.  *Hedef* ve *max_bytes* geçirilen değerler yoksayıldı.

*Kaynak* null değilse, işlev dizenin başlangıcında başlar ve kaydırma dizileri dahil olmak üzere sonraki UTF-8 çok baytlı karakterini tamamlaması gereken bayt sayısını belirlemede *max_bytes* bayta kadar inceler. İncelenen baytlar geçerli ve tam bir UTF-8 çok baytlı karakter içeriyorsa, işlev karakteri 16 bit veya 32 bitlik geniş karakter veya karakterlere dönüştürür. *Hedef* null değilse, işlev hedefteki ilk (ve muhtemelen yalnızca) sonuç karakterini depolar. Ek çıkış karakterleri gerekliyse, bir değer bir *durum* olarak ayarlanır, böylece işlevin sonraki çağrıları ek karakterlerin çıktısını verir ve-3 değerini döndürür. Daha fazla çıkış karakteri gerekmiyorsa, *durum* ilk kaydırma durumuna ayarlanır.

UTF-8 olmayan çok baytlı karakterleri UTF-16 LE karakterlerine dönüştürmek için [mbrtowc](mbrtowc.md), [mbtowc veya _mbtowc_l](mbtowc-mbtowc-l.md) işlevlerini kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üstbilgisi|
|--------------|--------------|------------------|
|**mbrtoc16**, **mbrtoc32**|\<uchar.h>|\<cuchar>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri dönüştürme](../data-conversion.md)\
[Ayarlar](../locale.md)\
[Çok baytlı karakter dizilerinin yorumu](../interpretation-of-multibyte-character-sequences.md)\
[c16rtomb, c32rtomb](c16rtomb-c32rtomb1.md)\
[mbrtowc](mbrtowc.md)\
[mbsrtowcs](mbsrtowcs.md)\
[mbsrtowcs_s](mbsrtowcs-s.md)
