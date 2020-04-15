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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 720b83dd48b42d77f35bce12f16e8ac79eb3b4d3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341659"
---
# <a name="_lsearch_s"></a>_lsearch_s

Bir değer için doğrusal arama yapar. [CRT](../../c-runtime-library/security-features-in-the-crt.md)Güvenlik Özellikleri açıklandığı gibi güvenlik geliştirmeleri ile [_lsearch](lsearch.md) bir sürümü.

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
Aranacak dizi tabanına işaretçi.

*number*<br/>
Öğe sayısı.

*Boyutu*<br/>
Baytlar'daki her dizi öğesinin boyutu.

*Karşılaştırmak*<br/>
Karşılaştırma yordamını işaretçi. İkinci parametre arama için anahtar için bir işaretçidir. Üçüncü parametre, anahtarla karşılaştırılması gereken bir dizi öğesiiçin bir işaretçidir.

*Bağlam*<br/>
Karşılaştırma işlevinde erişilebilen bir nesneye işaretçi.

## <a name="return-value"></a>Dönüş Değeri

*Anahtar* bulunursa, **_lsearch_s** *anahtarla*eşleşen *tabandaki* dizi öğesine bir işaretçi döndürür. *Anahtar* bulunamazsa, **_lsearch_s** dizinin sonunda yeni eklenen öğeye bir işaretçi döndürür.

Geçersiz parametreler işleve aktarılırsa, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütme devam etmesine izin verilirse, **errno** **EINVAL** olarak ayarlanır ve işlev **NULL**döndürür. Daha fazla bilgi için [bkz: errno, _doserrno, _sys_errlist ve _sys_nerr.](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)

### <a name="error-conditions"></a>Hata Koşulları

|*anahtar*|*base*|*Karşılaştırmak*|*number*|*Boyutu*|**Errno**|
|-----------|------------|---------------|-----------|------------|-------------|
|**Null**|herhangi bir|herhangi bir|herhangi bir|herhangi bir|**Eınval**|
|herhangi bir|**Null**|herhangi bir|!= 0|herhangi bir|**Eınval**|
|herhangi bir|herhangi bir|herhangi bir|herhangi bir|sıfır|**Eınval**|
|herhangi bir|herhangi bir|**Null**|a|herhangi bir|**Eınval**|

## <a name="remarks"></a>Açıklamalar

**_lsearch_s** işlevi, *her genişlik* baytı olan *bir dizi sayı* öğesindeki değer *anahtarı* için doğrusal bir arama gerçekleştirir. **bsearch_s**aksine, **_lsearch_s** dizi sıralanmış gerektirmez. *Anahtar* bulunamazsa, **_lsearch_s** dizi nin sonuna ekler ve artış *sayısı.*

*Karşılaştırma* işlevi, iki dizi öğesini karşılaştıran ve ilişkilerini belirten bir değer döndüren, kullanıcı tarafından sağlanan bir yordamın işaretçisidir. *Karşılaştırma* işlevi de işaretçiyi ilk bağımsız değişken olarak bağlama götürür. **_lsearch_s** aramaları, işaretçileri her çağrıda iki dizi öğesine geçirerek arama sırasında bir veya daha fazla kez *karşılaştırılır.* *karşılaştırmak* öğeleri karşılaştırmak ve daha sonra sıfırsız (yani öğeler farklı) veya 0 (yani öğeler aynı) döndürmelidir.

Aranan veri yapısı bir nesnenin parçasıysa ve *karşılaştırma* işlevinin nesnenin üyelerine erişmesi gerekiyorsa *bağlam* işaretçisi yararlı olabilir. Örneğin, *karşılaştırma* işlevindeki kod, geçersiz işaretçiyi uygun nesne türüne ve bu nesnenin üyelerine erişebilir. *Bağlam* işaretçisinin **eklenmesi,** verileri *karşılaştırma* işlevinde kullanılabilir hale getirmek için statik değişkenlerin kullanılmasıyla ilişkili yeniden canlandırma hatalarını önlemek için ek bağlam kullanılabildiği için _lsearch_s daha güvenli hale getirir.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_lsearch_s**|\<search.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Arama ve Sıralama](../../c-runtime-library/searching-and-sorting.md)<br/>
[bsearch_s](bsearch-s.md)<br/>
[_lfind_s](lfind-s.md)<br/>
[_lsearch](lsearch.md)<br/>
