---
title: _lsearch_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a680c990ec91edf225057ea729fd3343a57610d4
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="lsearchs"></a>_lsearch_s
Bir değer için doğrusal arama gerçekleştirir. Bir sürümünü [_lsearch](../../c-runtime-library/reference/lsearch.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void *_lsearch_s(  
   const void *key,  
   void *base,  
   unsigned int *num,  
   size_t size,  
   int (__cdecl *compare)(void *, const void *, const void *),  
   void * context  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `key`  
 Aranacak nesne.  
  
 `base`  
 Aranacak dizi tabanı işaretçi.  
  
 `num`  
 Öğe sayısı.  
  
 `size`  
 Her dizi öğesi bayt cinsinden boyutu.  
  
 `compare`  
 İşaretçi karşılaştırması yordama. İkinci parametre için arama anahtar bir işaretçidir. Üçüncü parametre anahtarla karşılaştırılması gereken bir dizi öğesine bir işaretçidir.  
  
 `context`  
 Karşılaştırma işlevinde erişilebilen bir nesne için bir işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Varsa `key` bulunan `_lsearch_s` dizisi öğesine bir işaretçi döndüren `base` eşleşen `key`. Varsa `key` bulunamadı, `_lsearch_s` dizinin sonuna en yeni eklenen öğesine bir işaretçi döndürür.  
  
 İşlev için geçersiz parametreler aktarılırsa geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Sonra devam etmek yürütülmesine izin veriliyorsa `errno` ayarlanır `EINVAL` ve işlevi döndürür `NULL`. Daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
### <a name="error-conditions"></a>Hata koşulları  
  
|`key`|`base`|`compare`|`num`|`size`|`errno`|  
|-----------|------------|---------------|-----------|------------|-------------|  
|`NULL`|tüm|tüm|tüm|tüm|`EINVAL`|  
|tüm|`NULL`|tüm|!= 0|tüm|`EINVAL`|  
|tüm|tüm|tüm|tüm|sıfır|`EINVAL`|  
|tüm|tüm|`NULL`|bir|tüm|`EINVAL`|  
  
## <a name="remarks"></a>Açıklamalar  
 `_lsearch_s` İşlevi gerçekleştiren değeri için doğrusal arama `key` dizisindeki `num` öğeleri, her biri `width` bayt sayısı. Farklı `bsearch_s`, `_lsearch_s` sıralanacak dizi gerektirmez. Varsa `key` , ardından bulunamadı `_lsearch_s` artırır ve dizinin sonuna ekler `num`.  
  
 `compare` İşlevi iki dizi öğeleri karşılaştırır ve ilişkilerini belirten bir değer döndürür ve kullanıcı tarafından sağlanan bir yordama bir işaretçidir. `compare` İşlevi de bağlamı ilk bağımsız değişken olarak işaretçisine alır. `_lsearch_s` çağrıları `compare` işaretçileri iki dizi öğelerinin her çağrıda geçirme, arama sırasında bir veya birden çok kez. `compare` gerekir ve öğeleri karşılaştırma ya da dönüş sıfır olmayan (öğeleri farklı olduğu anlamına gelir) veya 0 (öğeleri aynı olduğu anlamına gelir).  
  
 `context` İşaretçi Aranan veri yapısı bir nesnenin parçası ise yararlı olabilir ve `compare` işlevi nesnenin üyelerine erişme gerekiyor. Örneğin, kod `compare` işlevi uygun nesne türüne ve erişim üyeleri bu nesnenin void işaretçi çevirebilirsiniz. Eklenmesi `context` işaretçi yapar `_lsearch_s` daha güvenli ek bağlam verileri kullanılabilir hale getirmek için statik değişkenler kullanımıyla ilişkili yeniden giriş hataları önlemek için kullanılabileceğinden `compare` işlevi.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_lsearch_s`|\<Search.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arama ve sıralama](../../c-runtime-library/searching-and-sorting.md)   
 [bsearch_s](../../c-runtime-library/reference/bsearch-s.md)   
 [_lfind_s](../../c-runtime-library/reference/lfind-s.md)   
 [_lsearch](../../c-runtime-library/reference/lsearch.md)