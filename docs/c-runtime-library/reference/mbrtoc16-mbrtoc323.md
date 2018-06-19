---
title: mbrtoc16, mbrtoc323 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- mbrtoc16
- mbrtoc32
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
- mbrtoc16
- mbrtoc32
- uchar/mbrtoc16
- uchar/mbrtoc32
dev_langs:
- C++
helpviewer_keywords:
- mbrtoc16 function
- mbrtoc32 function
ms.assetid: 099ade4d-56f7-4e61-8b45-493f1d7a64bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a12e90f9a4bc0cc27df421c27d77a1b9b69334b9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405308"
---
# <a name="mbrtoc16-mbrtoc32"></a>mbrtoc16, mbrtoc32

İlk birden çok baytlı karakter dar bir dize, eşdeğer UTF-16 veya UTF-32 karakter çevirir.

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

*Hedef*<br/>
İşaretçi **char16_t** veya **char32_t** dönüştürmek için birden çok baytlı karakter eşdeğeridir. Null ise bir değer işlevi depolamaz.

*Kaynak*<br/>
İşaretçi dönüştürmek için birden çok baytlı karakter dizesi.

*max_bytes*<br/>
Bayt cinsinden en büyük sayısını *kaynak* dönüştürmek için bir karakter incelemek için. Bu bir ve içinde kalan tüm boş Sonlandırıcı dahil olmak üzere bayt sayısı arasında bir değer olmalıdır *kaynak*.

*Durumu*<br/>
İşaretçi bir **mbstate_t** dönüştürme durum nesnesi bir veya daha fazla çıkış karakter birden çok baytlı dizeye bilgilerini yorumlamak için kullanılacak.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa ilk değerini döndürür geçerli geçerlidir Bu koşullar, verilen *durumu* değeri:

|Değer|Koşul|
|-----------|---------------|
|0|Sonraki *max_bytes* veya daha az karakter gelen dönüştürülen *kaynak* durumunda depolanan değeri olan null geniş karakter için karşılık gelen *hedef* null değil.<br /><br /> *Durum* ilk kaydırma durumunu içerir.|
|1 arasında ve *max_bytes*(dahil)|Döndürülen değer bayt sayısıdır. *kaynak* geçerli bir birden çok baytlı karakter tamamlayın. Dönüştürülen geniş karakter durumunda depolanan *hedef* null değil.|
|-3|Bir önceki işlevi çağrısı kaynaklanan sonraki geniş karakter içinde depolanan *hedef* varsa *hedef* null değil. Hiçbir baytlar *kaynak* işlev çağrısı tarafından kullanılır.<br /><br /> Zaman *kaynak* işaret (örneğin, bir yedek çifti) göstermek için birden fazla geniş karakter gerektiriyorsa bir birden çok baytlı karakter sonra *durumu* değeri, böylece sonraki işlev çağrısı Yazar güncelleştirilir  out ek karakter.|
|-2|Sonraki *max_bytes* bayt temsil eden bir, ancak tamamlanmamış büyük olasılıkla geçerli, birden çok baytlı karakter. Hiçbir değer depolanan *hedef*. Bu sonuç ortaya çıkabilir *max_bytes* sıfırdır.|
|-1|Bir kodlama hatası oluştu. Sonraki *max_bytes* veya daha az sayıda bayt tam ve geçerli birden çok baytlı karakter katkıda bulunmamaktadır. Hiçbir değer depolanan *hedef*.<br /><br /> **EILSEQ** depolanan **errno** ve dönüştürme durumu *durumu* belirtilmedi.|

## <a name="remarks"></a>Açıklamalar

**Mbrtoc16** işlevi okur kadar *max_bytes* baytlar *kaynak* ilk tam, geçerli birden çok baytlı karakter ve ardından depoları eşdeğer UTF-16 bulmak için içinde karakteri *hedef*. Kaynak bayt geçerli iş parçacığı birden çok baytlı yerel ayar göre değerlendirilir. Birden çok baytlı karakter yedek çifti gibi birden fazla UTF-16 çıkış karakter gerektiriyorsa sonra *durumu* değeri sonraki UTF-16 karakteri depolamak için ayarlanır *hedef* sonrakiçağrıda**mbrtoc16**. **Mbrtoc32** işlevi ile aynıdır, ancak çıktı UTF-32 karakter olarak depolanır.

Varsa *kaynak* bir çağrı denk yapılan bağımsız kullanarak null, bu işlevlerin dönüş **NULL** için *hedef*, **""** için*kaynak*, için 1 *max_bytes*. Geçirilen değerlerini *hedef* ve *max_bytes* göz ardı edilir.

Varsa *kaynak* olan null, işlevi dizenin başında başlar ve en fazla inceler *max_bytes* sonraki birden çok baytlı karakter tamamlamak için gereken bayt sayısını belirlemek için bayt dahil Tüm shift sıralar. Examined bayt geçerli ve tam bir birden çok baytlı karakter içeriyorsa, işlev karakter eşdeğer 16 bit veya 32-bit geniş karakter ya da karakterlerini dönüştürür. Varsa *hedef* null olmayan ilk (ve muhtemelen yalnızca) sonuç karakter hedef işlevi mağazaları olan. Ek çıkış karakterleri gerekirse, bir değer kümesinde *durumu*, böylece işlevi yapılan sonraki çağrılar ek karakterler çıkış ve -3 değerini döndürür. Daha fazla çıkış karakter sonra gerekirse *durumu* ilk kaydırma durumuna ayarlanır.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üstbilgi|
|--------------|--------------|------------------|
|**mbrtoc16**, **mbrtoc32**|\<UCHAR.h >|\<cuchar >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[c16rtomb, c32rtomb](c16rtomb-c32rtomb1.md)<br/>
[mbrtowc](mbrtowc.md)<br/>
[mbsrtowcs](mbsrtowcs.md)<br/>
[mbsrtowcs_s](mbsrtowcs-s.md)<br/>
