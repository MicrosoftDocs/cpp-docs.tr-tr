---
title: _lsearch_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- linear searching
- values, searching for
- keys, finding in arrays
- arrays [CRT], searching
- searching, linear
- _lsearch_s function
- lsearch_s function
ms.assetid: d2db0635-be7a-4799-8660-255f14450882
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 12315350b62673abb0a838f9d30830354c58da73
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="lsearchs"></a>_lsearch_s

Bir değer için doğrusal arama gerçekleştirir. Bir sürümünü [_lsearch](lsearch.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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
Aranacak dizi tabanı işaretçi.

*Sayı*<br/>
Öğe sayısı.

*Boyutu*<br/>
Her dizi öğesi bayt cinsinden boyutu.

*Karşılaştırma*<br/>
İşaretçi karşılaştırması yordama. İkinci parametre için arama anahtar bir işaretçidir. Üçüncü parametre anahtarla karşılaştırılması gereken bir dizi öğesine bir işaretçidir.

*bağlam*<br/>
Karşılaştırma işlevinde erişilebilen bir nesne için bir işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Varsa *anahtar* bulunan **_lsearch_s** dizisi öğesine bir işaretçi döndürür *temel* eşleşen *anahtar*. Varsa *anahtar* bulunamadı, **_lsearch_s** dizinin sonuna en yeni eklenen öğesine bir işaretçi döndürür.

İşlev için geçersiz parametreler aktarılırsa geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Sonra devam etmek yürütülmesine izin veriliyorsa **errno** ayarlanır **EINVAL** ve işlevi döndürür **NULL**. Daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

### <a name="error-conditions"></a>Hata koşulları

|*Anahtarı*|*base*|*Karşılaştırma*|*Sayı*|*Boyutu*|**errno**|
|-----------|------------|---------------|-----------|------------|-------------|
|**NULL**|tüm|tüm|tüm|tüm|**EINVAL**|
|tüm|**NULL**|tüm|!= 0|tüm|**EINVAL**|
|tüm|tüm|tüm|tüm|sıfır|**EINVAL**|
|tüm|tüm|**NULL**|bir|tüm|**EINVAL**|

## <a name="remarks"></a>Açıklamalar

**_Lsearch_s** işlevi gerçekleştiren değeri için doğrusal arama *anahtar* dizisindeki *numarası* öğeleri, her biri *genişliği* bayt. Farklı **bsearch_s**, **_lsearch_s** sıralanacak dizi gerektirmez. Varsa *anahtar* , ardından bulunamadı **_lsearch_s** artırır ve dizinin sonuna ekler *numarası*.

*Karşılaştırmak* işlevi iki dizi öğeleri karşılaştırır ve ilişkilerini belirten bir değer döndürür ve kullanıcı tarafından sağlanan bir yordama bir işaretçidir. *Karşılaştırmak* işlevi de bağlamı ilk bağımsız değişken olarak işaretçisine alır. **_lsearch_s** çağrıları *karşılaştırmak* işaretçileri iki dizi öğelerinin her çağrıda geçirme, arama sırasında bir veya birden çok kez. *Karşılaştırma* gerekir ve öğeleri karşılaştırma ya da dönüş sıfır olmayan (öğeleri farklı olduğu anlamına gelir) veya 0 (öğeleri aynı olduğu anlamına gelir).

*Bağlamı* işaretçi Aranan veri yapısı bir nesnenin parçası ise yararlı olabilir ve *karşılaştırmak* işlevi nesnenin üyelerine erişme gerekiyor. Örneğin, kod *karşılaştırmak* işlevi uygun nesne türüne ve erişim üyeleri bu nesnenin void işaretçi çevirebilirsiniz. Eklenmesi *bağlamı* işaretçi yapar **_lsearch_s** daha güvenli çünkü ek bağlam verileri kullanılabilir hale getirmek için statik değişkenler kullanımıyla ilişkili yeniden giriş hataları önlemek için kullanılabilir *karşılaştırmak* işlevi.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_lsearch_s**|\<Search.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Arama ve Sıralama](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch_s](bsearch-s.md)<br/>
[_lfind_s](lfind-s.md)<br/>
[_lsearch](lsearch.md)<br/>
