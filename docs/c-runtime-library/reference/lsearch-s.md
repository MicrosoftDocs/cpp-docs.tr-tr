---
title: _lsearch_s
ms.date: 11/04/2016
apiname:
- _lsearch_s
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _lsearch_s
- lsearch_s
helpviewer_keywords:
- linear searching
- values, searching for
- keys, finding in arrays
- arrays [CRT], searching
- searching, linear
- _lsearch_s function
- lsearch_s function
ms.assetid: d2db0635-be7a-4799-8660-255f14450882
ms.openlocfilehash: f57a96622419e3f72fc2df5b260cbbbdd59666ae
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677012"
---
# <a name="lsearchs"></a>_lsearch_s

Bir değer için doğrusal bir arama gerçekleştirir. Bir sürümünü [_lsearch](lsearch.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sözdizimi

```C
void *_lsearch_s(
   const void *key,
   void *base,
   unsigned int *num,
   size_t size,
   int (__cdecl *compare)(void *, const void *, const void *),
   void * context
);
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Aranacak nesne.

*base*<br/>
Temel arama yapılacak dizinin işaretçisi.

*Sayı*<br/>
Öğe sayısı.

*Boyutu*<br/>
Her dizi öğesi bayt cinsinden boyutu.

*Karşılaştırma*<br/>
Karşılaştırma yordamı işaretçisi. İkinci parametre arama anahtarı bir işaretçisidir. Üçüncü parametresi, anahtar ile karşılaştırılacak bir dizi öğesinin işaretçisidir.

*Bağlam*<br/>
Karşılaştırma işlev erişilebilen bir nesne için bir işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Varsa *anahtarı* bulunursa **_lsearch_s** dizisi öğeye bir işaretçi döndürür *temel* eşleşen *anahtar*. Varsa *anahtarı* bulunamazsa **_lsearch_s** dizinin sonuna yeni eklenen öğeye bir işaretçi döndürür.

Geçersiz parametreler bir işleve geçirilirse geçersiz parametre işleyicisi açıklandığı gibi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme, ardından devam etmesine izin verilirse **errno** ayarlanır **EINVAL** ve işlev döndürür **NULL**. Daha fazla bilgi için [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

### <a name="error-conditions"></a>Hata koşulları

|*Anahtarı*|*base*|*Karşılaştırma*|*Sayı*|*Boyutu*|**errno**|
|-----------|------------|---------------|-----------|------------|-------------|
|**NULL**|Tüm|Tüm|Tüm|Tüm|**EINVAL**|
|Tüm|**NULL**|Tüm|!= 0|Tüm|**EINVAL**|
|Tüm|Tüm|Tüm|Tüm|sıfır|**EINVAL**|
|Tüm|Tüm|**NULL**|Bir|Tüm|**EINVAL**|

## <a name="remarks"></a>Açıklamalar

**_Lsearch_s** işlevi, doğrusal bir arama değeri gerçekleştirir *anahtarı* bir dizide *numarası* öğeleri, her biri *genişliği* bayt. Farklı **bsearch_s**, **_lsearch_s** sıralanacak dizi gerektirmez. Varsa *anahtarı* , ardından bulunamadı **_lsearch_s** artırır ve dizi sonuna ekler *numarası*.

*Karşılaştırma* işlevi kullanıcı tarafından sağlanan iki diziyi öğe karşılaştırır ve bunların belirten bir değeri döndüren bir yordam işaretçidir. *Karşılaştırma* işlevi ayrıca bir işaretçi bağlamı ilk bağımsız değişken olarak alır. **_lsearch_s** çağrıları *karşılaştırma* işaretçileri iki dizi öğelerine her çağrıda geçirme, arama sırasında bir veya daha fazla kez. *Karşılaştırma* gerekir ve öğeleri karşılaştırma ya da dönüş sıfır olmayan (öğeleri farklı olduğu anlamına gelir) veya 0 (öğeleri aynı olduğu anlamına gelir).

*Bağlam* işaretçi Aranan veri yapısı, bir nesnenin parçası ise kullanışlı olabilir ve *karşılaştırmak* işlevi bir nesnenin üyelerine erişim gerekir. Örneğin, kod *karşılaştırma* işlevi uygun nesne türü ve erişim üyeleri o nesnenin void işaretçisine çevirebilirsiniz. Ek *bağlam* işaretçisi yapar **_lsearch_s** daha güvenli veri kullanılabilir hale getirmek için statik değişkenler kullanmayla ilişkili yeniden giriş hataları önlemek için ek bağlam kullanılabildiğinden *karşılaştırma* işlevi.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_lsearch_s**|\<Search.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Arama ve Sıralama](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch_s](bsearch-s.md)<br/>
[_lfind_s](lfind-s.md)<br/>
[_lsearch](lsearch.md)<br/>
