---
title: _lsearch_s
ms.date: 4/2/2020
api_name:
- _lsearch_s
- _o__lsearch_s
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: d8c421eb3c7a6a617ce073cbf5f36416294c1874
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82920452"
---
# <a name="_lsearch_s"></a>_lsearch_s

Bir değer için doğrusal bir arama gerçekleştirir. [CRT Içindeki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleriyle [_lsearch](lsearch.md) bir sürümü.

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

*number*<br/>
Öğe sayısı.

*boyutla*<br/>
Her dizi öğesinin bayt cinsinden boyutu.

*Karşılaştır*<br/>
Karşılaştırma yordamının işaretçisi. İkinci parametre, arama için anahtarın bir işaretçisidir. Üçüncü parametre, anahtar ile Karşılaştırılacak dizi öğesine yönelik bir işaretçidir.

*bağlam*<br/>
Karşılaştırma işlevinde erişilebilir olabilecek bir nesne işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

*Anahtar* bulunursa **_lsearch_s** , *tabanında* eşleşen dizinin öğesine bir işaretçi *döndürür.* *Anahtar* bulunamazsa, **_lsearch_s** dizinin sonunda yeni eklenen öğeye bir işaretçi döndürür.

İşleve geçersiz parametreler geçirilmemişse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, **errno** **EINVAL** olarak ayarlanır ve işlev **null**değerini döndürür. Daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

### <a name="error-conditions"></a>Hata koşulları

|*anahtar*|*base*|*Karşılaştır*|*number*|*boyutla*|**errno**|
|-----------|------------|---------------|-----------|------------|-------------|
|**DEĞER**|kaydedilmemiş|kaydedilmemiş|kaydedilmemiş|kaydedilmemiş|**EıNVAL**|
|kaydedilmemiş|**DEĞER**|kaydedilmemiş|! = 0|kaydedilmemiş|**EıNVAL**|
|kaydedilmemiş|kaydedilmemiş|kaydedilmemiş|kaydedilmemiş|sıfır|**EıNVAL**|
|kaydedilmemiş|kaydedilmemiş|**DEĞER**|a|kaydedilmemiş|**EıNVAL**|

## <a name="remarks"></a>Açıklamalar

**_Lsearch_s** işlevi, her *Genişlik* baytından oluşan *sayı* öğeleri dizisindeki değer *anahtarı* için doğrusal bir arama gerçekleştirir. **Bsearch_s**aksine, **_lsearch_s** dizinin sıralanmasını gerektirmez. *Anahtar* bulunmazsa **_lsearch_s** dizinin sonuna ve Artımlar *sayısına*ekler.

*Compare* işlevi, iki dizi öğesini karşılaştıran ve ilişkilerini belirten bir değer döndüren kullanıcı tarafından sağlanan yordamın bir işaretçisidir. *Compare* işlevi, ilk bağımsız değişken olarak bağlam işaretçisini de alır. **_lsearch_s** çağrılar arama sırasında bir veya daha fazla kez *karşılaştırıp* her çağrıda iki dizi öğesine işaretçiler geçirerek. *Compare* öğeleri karşılaştırmalıdır ve sıfır dışında bir değere (öğelerin farklı olduğu anlamına gelir) veya 0 (öğeler özdeş) döndürmelidir.

Arama veri yapısı bir nesnenin parçasıysa ve *Compare* işlevinin nesnenin üyelerine erişmesi gerekiyorsa *bağlam* işaretçisi yararlı olabilir. Örneğin, *Compare* işlevindeki kod void işaretçisini uygun nesne türüne ve bu nesnenin üyelerine ekleyebilir. *Bağlam* işaretçisinin eklenmesi, verileri *karşılaştırma* işlevine uygun hale getirmek için statik değişkenlerle ilişkili hataların yeniden giriş oluşmasını önlemek için daha güvenli **_lsearch_s** hale getirir.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_lsearch_s**|\<Search. h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Arama ve sıralama](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch_s](bsearch-s.md)<br/>
[_lfind_s](lfind-s.md)<br/>
[_lsearch](lsearch.md)<br/>
