---
title: _lsearch_s
ms.date: 11/04/2016
api_name:
- _lsearch_s
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
- api-ms-win-crt-utility-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 1c3c0ac41a4805acb558c75fb5ff4cbc0e3aa838
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70953021"
---
# <a name="_lsearch_s"></a>_lsearch_s

Bir değer için doğrusal bir arama gerçekleştirir. [CRT 'Daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleriyle [_lsearch](lsearch.md) 'ün bir sürümü.

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

*anahtar*<br/>
Aranacak nesne.

*base*<br/>
Aranacak dizinin tabanına yönelik işaretçi.

*sayısından*<br/>
Öğe sayısı.

*boyutla*<br/>
Her dizi öğesinin bayt cinsinden boyutu.

*Karşılaştır*<br/>
Karşılaştırma yordamının işaretçisi. İkinci parametre, arama için anahtarın bir işaretçisidir. Üçüncü parametre, anahtar ile Karşılaştırılacak dizi öğesine yönelik bir işaretçidir.

*bağlam*<br/>
Karşılaştırma işlevinde erişilebilir olabilecek bir nesne işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

*Anahtar* bulunursa, **_lsearch_s** , *tabanında* eşleşen dizinin öğesine bir işaretçi *döndürür.* *Anahtar* bulunamazsa, **_lsearch_s** dizinin sonunda yeni eklenen öğeye yönelik bir işaretçi döndürür.

İşleve geçersiz parametreler geçirilmemişse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, **errno** **EINVAL** olarak ayarlanır ve işlev **null**değerini döndürür. Daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

### <a name="error-conditions"></a>Hata koşulları

|*anahtar*|*base*|*Karşılaştır*|*sayısından*|*boyutla*|**errno**|
|-----------|------------|---------------|-----------|------------|-------------|
|**DEĞER**|Kaydedilmemiş|Kaydedilmemiş|Kaydedilmemiş|Kaydedilmemiş|**EINVAL**|
|Kaydedilmemiş|**DEĞER**|Kaydedilmemiş|!= 0|Kaydedilmemiş|**EINVAL**|
|Kaydedilmemiş|Kaydedilmemiş|Kaydedilmemiş|Kaydedilmemiş|sıfır|**EINVAL**|
|Kaydedilmemiş|Kaydedilmemiş|**DEĞER**|Kızılötesi|Kaydedilmemiş|**EINVAL**|

## <a name="remarks"></a>Açıklamalar

**_Lsearch_s** işlevi, her bir *Genişlik* baytından oluşan *sayı* öğeleri dizisindeki değer *anahtarı* için doğrusal bir arama gerçekleştirir. **Bsearch_s**aksine, **_lsearch_s** öğesinin sıralanmasını gerektirmez. *Anahtar* bulunamazsa, **_lsearch_s** onu dizinin sonuna ekler ve *sayı*artar.

*Compare* işlevi, iki dizi öğesini karşılaştıran ve ilişkilerini belirten bir değer döndüren kullanıcı tarafından sağlanan yordamın bir işaretçisidir. *Compare* işlevi, ilk bağımsız değişken olarak bağlam işaretçisini de alır. **_lsearch_s** çağrıları, arama sırasında bir veya daha fazla kez *karşılaştırıp* her çağrıda iki dizi öğesine işaretçiler geçirerek. *Compare* öğeleri karşılaştırmalıdır ve sıfır dışında bir değere (öğelerin farklı olduğu anlamına gelir) veya 0 (öğeler özdeş) döndürmelidir.

Arama veri yapısı bir nesnenin parçasıysa ve *Compare* işlevinin nesnenin üyelerine erişmesi gerekiyorsa *bağlam* işaretçisi yararlı olabilir. Örneğin, *Compare* işlevindeki kod void işaretçisini uygun nesne türüne ve bu nesnenin üyelerine ekleyebilir. *Bağlam* işaretçisinin eklenmesi, verileri *karşılaştırma* işlevine uygun hale getirmek için statik değişkenleri kullanmayla ilişkili hataların yeniden giriş yapmasını önlemek için **_lsearch_s** daha güvenli hale getirir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_lsearch_s**|\<Search. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Arama ve Sıralama](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch_s](bsearch-s.md)<br/>
[_lfind_s](lfind-s.md)<br/>
[_lsearch](lsearch.md)<br/>
