---
title: _putenv, _wputenv | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _putenv
- _wputenv
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
- api-ms-win-crt-environment-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tputenv
- _wputenv
- _putenv
- wputenv
- tputenv
dev_langs:
- C++
helpviewer_keywords:
- _putenv function
- environment variables, deleting
- putenv function
- tputenv function
- environment variables, creating
- wputenv function
- _wputenv function
- _tputenv function
- environment variables, modifying
ms.assetid: 9ba9b7fd-276e-45df-8420-d70c4204b8bd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 12b1379ea70c841f1689a8b83fae7ca7f43f5789
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="putenv-wputenv"></a>_putenv, _wputenv
Oluşturur, değiştirir veya ortam değişkenleri kaldırır. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [_putenv_s, _wputenv_s](../../c-runtime-library/reference/putenv-s-wputenv-s.md).  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _putenv(  
   const char *envstring   
);  
int _wputenv(  
   const wchar_t *envstring   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `envstring`  
 Ortam dizesinin tanımı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa 0 veya bir hata durumunda -1 döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `_putenv` İşlevi yeni ortam değişkenlerini ekler veya varolan ortam değişkenlerinin değerlerini değiştirir. Ortam değişkenleri, bir işlemi (örneğin, bir programla bağlanması kitaplıkları için varsayılan arama yolu) yürütür ortamı tanımlayın. `_wputenv` bir joker karakter sürümü `_putenv`; `envstring` bağımsız değişkeni `_wputenv` bir joker karakter dizesidir.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tputenv`|`_putenv`|`_putenv`|`_wputenv`|  
  
 `envstring` Bağımsız değişkeni bir işaretçi biçiminde bir dize olmalıdır `varname=string`, burada `varname` eklenemez veya değiştirilemez için ortam değişkeni adı ve `string` değişkenin değeridir. Varsa `varname` zaten ortamının bir parçası olan kendi değer ile değiştirilir `string`; Aksi takdirde, yeni `varname` değişkeni ve onun `string` değeri ortama eklenir. Boş bir belirterek ortamından bir değişkeni kaldırabilirsiniz `string` — diğer bir deyişle, belirterek yalnızca `varname=`.  
  
 `_putenv` ve `_wputenv` geçerli işlem için yerel olan ortam etkiler; komutu düzeyi ortamı değiştirmek için kullanamazsınız. Diğer bir deyişle, bu işlevler yalnızca veri yapılarını Çalışma Zamanı Kitaplığı'na erişilebilir ve olmayan bir işlem için işletim sistemi tarafından oluşturulan ortamı segment çalışır. Geçerli işlem sonlandırıldığında ortamı düzeyine (çoğu durumda, işletim sistemi düzeyinde) çağırma işleminin geri döner. Ancak, değiştirilmiş ortamı tarafından oluşturulan tüm yeni işlemleri için geçirilebilir `_spawn`, `_exec`, veya `system`, ve bu yeni işlemler tarafından eklenen tüm yeni öğeler `_putenv` ve `_wputenv`.  
  
 Bir ortam giriş doğrudan değiştirmeyin: bunun yerine, kullanın `_putenv` veya `_wputenv` değiştirmek için. Özellikle, doğrudan öğeleri boşaltma `_environ[]` genel dizi ele alınan geçersiz bellek neden.  
  
 `getenv` ve `_putenv` genel değişkeni kullanmak `_environ` ortamı tablosu; erişmek için `_wgetenv` ve `_wputenv` kullanmak `_wenviron`. `_putenv` ve `_wputenv` değerini değişebilir `_environ` ve `_wenviron`, böylece geçersiz kılmalarını `_envp` bağımsız değişkeni `main` ve `_wenvp` bağımsız değişkeni `wmain`. Bu nedenle, kullanmak daha güvenli `_environ` veya `_wenviron` ortamı bilgilere erişmek için. İlişkisi hakkında daha fazla bilgi için `_putenv` ve `_wputenv` genel değişkenler için bkz: [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).  
  
> [!NOTE]
>  `_putenv` Ve `_getenv` işlevleri aileleri iş parçacığı açısından güvenli değildir. `_getenv` dize işaretçisi sırasında döndürebilirsiniz `_putenv` rastgele hatalarına neden dize değiştiriyor. Bu işlevler çağrıları eşitlendiğinden emin olun.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_putenv`|\<stdlib.h>|  
|`_wputenv`|\<stdlib.h > veya \<wchar.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
 Nasıl kullanılacağına ilişkin bir örnek için `_putenv`, bkz: [getenv, _wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Süreç ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)   
 [GETENV, _wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md)   
 [_searchenv, _wsearchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md)