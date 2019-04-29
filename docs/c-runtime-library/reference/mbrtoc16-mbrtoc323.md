---
title: mbrtoc16, mbrtoc323
ms.date: 11/04/2016
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
helpviewer_keywords:
- mbrtoc16 function
- mbrtoc32 function
ms.assetid: 099ade4d-56f7-4e61-8b45-493f1d7a64bd
ms.openlocfilehash: f8573ac321772d19141be0228891b290ba48b217
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331590"
---
# <a name="mbrtoc16-mbrtoc32"></a>mbrtoc16, mbrtoc32

İlk çok baytlı karakteri bir dar dize ile eşdeğer UTF-16 veya UTF-32 karakter çevirir.

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
İşaretçi **char16_t** veya **char32_t** dönüştürülecek çok baytlı karakter eşdeğeridir. Null ise, işlev bir değer depolamaz.

*source*<br/>
Dönüştürülecek çok baytlı karakter dize işaretçisi.

*max_bytes*<br/>
En fazla bayt sayısını *kaynak* bir karakteri dönüştürmek incelemek için. Bu bir ve içinde kalan null sonlandırıcıyı da dahil olmak üzere, bayt sayısı arasında bir değer olmalıdır *kaynak*.

*durumu*<br/>
İşaretçi bir **mbstate_t** bir veya daha fazla karakterleri çıkarmak için çok baytlı dize yorumlamak için kullanılan dönüştürme durum nesnesi.

## <a name="return-value"></a>Dönüş Değeri

Başarı durumunda ilk değerini döndürür. geçerli uygular Bu koşullar, verilen *durumu* değeri:

|Değer|Koşul|
|-----------|---------------|
|0|Sonraki *max_bytes* ya da daha az karakter gelen *kaynak* durumunda depolanan değeri olan null geniş karakter için karşılık gelen *hedef* null değil.<br /><br /> *Durum* ilk shift durumunu içerir.|
|1 arasındaki ve *max_bytes*(dahil)|Döndürülen değer bayt sayısıdır. *kaynak* geçerli çok baytlı bir karakterin tamamlayın. Dönüştürülen geniş karakter durumunda depolanan *hedef* null değil.|
|-3|Bir önceki işlev çağrısından kaynaklanan bulunan sonraki geniş karakterin içinde depolanan *hedef* varsa *hedef* null değil. Hiçbir bayt *kaynak* bu işleve çağrı tarafından kullanılır.<br /><br /> Zaman *kaynak* işaret (örneğin, bir yedek çifti) göstermek için birden fazla geniş karakter gerektiren bir çok baytlı karakterin ardından *durumu* değeri, böylece sonraki işlev çağrısı Yazar güncelleştirilir  out ek karakter.|
|-2|Sonraki *max_bytes* bayt temsil eden bir eksik, ancak büyük olasılıkla geçerli, çok baytlı karakter. Hiçbir değer depolanan *hedef*. Bu sonucu ortaya çıkabilir *max_bytes* sıfırdır.|
|-1|Bir kodlama hatası oluştu. Sonraki *max_bytes* veya daha az bayt tam ve geçerli çok baytlı karakter katkıda bulunmuyor. Hiçbir değer depolanan *hedef*.<br /><br /> **EILSEQ** depolanan **errno** ve dönüştürme durumu *durumu* belirtilmemiş.|

## <a name="remarks"></a>Açıklamalar

**Mbrtoc16** işlevi okur kadar *max_bytes* bayt *kaynak* ilk tam, geçerli çok baytlı karakteri ve ardından depoları eşdeğer UTF-16 bulmak için karakter olarak *hedef*. Kaynak bayt iş parçacığı geçerli çok baytlı yerel göre yorumlanır. Çok baytlı karakterin bir yedek çifti gibi birden fazla UTF-16 çıkış karakter gerektiriyorsa, ardından *durumu* değeri ayarı sonraki UTF-16 karakter depolamak için *hedef* yapılansonrakiçağrıda**mbrtoc16**. **Mbrtoc32** işlevi ile aynıdır, ancak çıkış bir UTF-32 karakter olarak depolanır.

Varsa *kaynak* null çağrı bir denk yapılan bağımsız değişkenleri kullanarak, bu işlevlerin dönüş **NULL** için *hedef*, **""** için*kaynak*, için ve 1 *max_bytes*. Geçirilen değerlerini *hedef* ve *max_bytes* göz ardı edilir.

Varsa *kaynak* olduğu null, işlev dize başlangıcında başlar ve en fazla inceler *max_bytes* sonraki çok baytlı karakteri tamamlamak için gereken bayt sayısını belirlemek için bayt dahil olmak üzere herhangi bir üst karakter dizileri. Examined bayt geçerli ve tam bir çok baytlı karakter içeriyorsa, işlev karakteri eşdeğer 16-bit veya 32-bit geniş karakter veya karakterler dönüştürür. Varsa *hedef* null olmayan ilk (ve muhtemelen tek) sonucu karakter hedef işlevi depoları olan. Ek çıkış karakteri gerekiyorsa, bir değer kümesindeki *durumu*, böylece işlevine yapılan sonraki çağrılar ek karakterleri çıkış ve -3 değerini döndürür. Daha fazla çıkış karakter ardından, gerekliyse *durumu* ilk shift durumuna ayarlanır.

## <a name="requirements"></a>Gereksinimler

|İşlev|C üstbilgisi|C++ üst bilgisi|
|--------------|--------------|------------------|
|**mbrtoc16**, **mbrtoc32**|\<UCHAR.h >|\<cuchar >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[c16rtomb, c32rtomb](c16rtomb-c32rtomb1.md)<br/>
[mbrtowc](mbrtowc.md)<br/>
[mbsrtowcs](mbsrtowcs.md)<br/>
[mbsrtowcs_s](mbsrtowcs-s.md)<br/>
