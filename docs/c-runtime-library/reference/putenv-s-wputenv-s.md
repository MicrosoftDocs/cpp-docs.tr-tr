---
title: _putenv_s, _wputenv_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wputenv_s
- _putenv_s
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
apitype: DLLExport
f1_keywords:
- putenv_s
- wputenv_s
- _wputenv_s
- _putenv_s
dev_langs: C++
helpviewer_keywords:
- wputenv_s function
- _putenv_s function
- environment variables, deleting
- putenv_s function
- _wputenv_s function
- environment variables, creating
- environment variables, modifying
ms.assetid: fbf51225-a8da-4b9b-9d7c-0b84ef72df18
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b7d55736daf6652ecbde6b0d16256ccebc206bb5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="putenvs-wputenvs"></a>_putenv_s, _wputenv_s
Oluşturur, değiştirir veya ortam değişkenleri kaldırır. Sürümleri bunlar [_putenv, _wputenv](../../c-runtime-library/reference/putenv-wputenv.md) ancak güvenlik geliştirmeleri açıklandığı gibi sahip [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [/ZW ile desteklenmeyen CRT işlevleri](http://msdn.microsoft.com/en-us/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
errno_t _putenv_s(  
   const char *name,  
   const char *value   
);  
errno_t _wputenv_s(  
   const wchar_t *name,  
   const wchar_t *value  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `name`  
 Ortam değişkeni adı.  
  
 `value`  
 Ortam değişkeni ayarlanacak değer.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa 0 döndürür veya bir hata kodu.  
  
### <a name="error-conditions"></a>Hata koşulları  
  
|`name`|`value`|Dönüş değeri|  
|------------|-------------|------------------|  
|`NULL`|tüm|`EINVAL`|  
|tüm|`NULL`|`EINVAL`|  
  
 Bir hata koşullarını ortaya çıkarsa, bu işlevlerin bir geçersiz parametre işleyicisi açıklandığı gibi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütme devam etmek için izin verilip verilmediğini, bu işlevlerin dönüş `EINVAL` ve `errno` için `EINVAL`.  
  
## <a name="remarks"></a>Açıklamalar  
 `_putenv_s` İşlevi yeni ortam değişkenlerini ekler veya varolan ortam değişkenlerinin değerlerini değiştirir. Ortam değişkenleri, bir işlemi (örneğin, bir programla bağlanması kitaplıkları için varsayılan arama yolu) yürütür ortamı tanımlayın. `_wputenv_s`bir joker karakter sürümü `_putenv_s`; `envstring` bağımsız değişkeni `_wputenv_s` bir joker karakter dizesidir.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tputenv_s`|`_putenv_s`|`_putenv_s`|`_wputenv_s`|  
  
 `name`eklenen veya değiştirilecek ortam değişkeni adı ve `value` değişkenin değeridir. Varsa `name` zaten ortamının bir parçası olan kendi değer ile değiştirilir `value`; Aksi takdirde, yeni `name` değişkeni ve onun `value` ortama eklenir. Boş bir dize belirterek ortamından bir değişkeni kaldırabilirsiniz (diğer bir deyişle, "") için `value`.  
  
 `_putenv_s`ve `_wputenv_s` geçerli işlem için yerel olan ortam etkiler; komutu düzeyi ortamı değiştirmek için kullanamazsınız. Bu işlevler Çalışma Zamanı Kitaplığı'na erişilebilen veri yapılarını ve "işletim sistemi için bir işlem oluşturur segment" ortam üzerinde çalışır. Geçerli işlem sonlandırıldığında ortamı çoğu durumda işletim sistemi düzeyi arama işlemi düzeyine geri döndürür. Ancak, değiştirilmiş ortamı tarafından oluşturulan tüm yeni işlemleri için geçirilebilir `_spawn`, `_exec`, veya `system`, ve bu yeni işlemler tarafından eklenen tüm yeni öğeler `_putenv_s` ve `_wputenv_s`.  
  
 Bir ortam giriş doğrudan değiştirmeyin; Bunun yerine, kullanın `_putenv_s` veya `_wputenv_s` değiştirmek için. Özellikle, doğrudan öğeleri boşaltma `_environ[]` genel dizi ele alınması için geçersiz bellek neden olabilir.  
  
 `getenv`ve `_putenv_s` genel değişkeni kullanmak `_environ` ortamı tablosu; erişmek için `_wgetenv` ve `_wputenv_s` kullanmak `_wenviron`. `_putenv_s`ve `_wputenv_s` değerini değişebilir `_environ` ve `_wenviron`ve böylece geçersiz `envp` bağımsız değişkeni `main` ve `_wenvp` bağımsız değişkeni `wmain`. Bu nedenle, kullanmak daha güvenli `_environ` veya `_wenviron` ortamı bilgilere erişmek için. Arasındaki ilişki hakkında daha fazla bilgi için `_putenv_s` ve `_wputenv_s` genel değişkenler için bkz: [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).  
  
> [!NOTE]
>  `_putenv_s` Ve `_getenv_s` işlevleri aileleri iş parçacığı açısından güvenli değildir. `_getenv_s`dize işaretçisi sırasında döndürebilirsiniz `_putenv_s` dizesini değiştirmeyi ve böylece rastgele hatalara neden. Bu işlevler çağrıları eşitlendiğinden emin olun.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_putenv_s`|\<stdlib.h >|  
|`_wputenv_s`|\<stdlib.h > veya \<wchar.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
 Nasıl kullanılacağını gösteren bir örnek için `_putenv_s`, bkz: [getenv_s, _wgetenv_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Süreç ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)   
 [GETENV, _wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md)   
 [_searchenv, _wsearchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md)