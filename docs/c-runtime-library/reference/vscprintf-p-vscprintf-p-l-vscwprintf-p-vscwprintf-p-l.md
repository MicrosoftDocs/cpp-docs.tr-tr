---
title: _vscprintf_p, _vscprintf_p_l, _vscwprintf_p, _vscwprintf_p_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _vscprintf_p_l
- _vscprintf_p
- _vscwprintf_p_l
- _vscwprintf_p
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
- _vscprintf_p
- _vscprintf_p_l
- vscwprintf_p
- vscprintf_p
- vscwprintf_p_l
- _vscwprintf_p_l
- vscprintf_p_l
- _vscwprintf_p
dev_langs: C++
helpviewer_keywords:
- vscprintf_p function
- _vsctprintf_p_l function
- vscwprintf_p_l function
- _vscwprintf_p_l function
- _vscprintf_p function
- vsctprintf_p function
- _vscprintf_p_l function
- _vscwprintf_p function
- vscwprintf_p function
- vsctprintf_p_l function
- _vsctprintf_p function
- vscprintf_p_l function
ms.assetid: 5da920b3-8652-4ee9-b19e-5aac3ace9d03
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b920931cf524ef44d1c09814576dbf22e54a640b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="vscprintfp-vscprintfpl-vscwprintfp-vscwprintfpl"></a>_vscprintf_p, _vscprintf_p_l, _vscwprintf_p, _vscwprintf_p_l
Bağımsız değişkenler kullanılan order belirtme olanağı bir işaretçi bağımsız değişken listesini kullanarak biçimlendirilmiş dizesindeki karakterlerin sayısını döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _vscprintf_p(  
   const char *format,  
   va_list argptr   
);  
int _vscprintf_p _l(  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);  
int _vscwprintf_p (  
   const wchar_t *format,  
   va_list argptr   
);  
int _vscwprintf_p _l(  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `format`  
 Biçim denetimi dizesi.  
  
 `argptr`  
 İşaretçi bağımsız değişken listesi.  
  
 `locale`  
 Kullanılacak yerel ayar.  
  
 Daha fazla bilgi için bkz: [biçim belirtimleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## <a name="return-value"></a>Dönüş Değeri  
 `_vscprintf_p`dize işaret varsa, bağımsız değişkenleri listesi tarafından oluşturulan karakter sayısını yazdırılması veya bir dosyayı veya belirtilen biçimlendirme kodlarını kullanarak arabellek gönderilen döndürür. Döndürülen değer sonlandırma null karakteri içermez. `_vscwprintf_p`geniş karakterler için aynı işlevi gerçekleştirir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlevler farklı `_vscprintf` ve `_vscwprintf` bağımsız değişkenleri kullanıldığı sırayı belirtme olanağı yalnızca destekledikleri olmasıdır. Daha fazla bilgi için bkz: [printf_p konumsal parametreler](../../c-runtime-library/printf-p-positional-parameters.md).  
  
 Bu işlevleri sürümlerini `_l` soneki, geçerli iş parçacığı yerel ayar yerine geçirilen yerel ayar parametresi kullanmasını dışında aynıdır.  
  
 Varsa `format` null işaretçi açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, işlevleri -1 döndürür ve `errno` için `EINVAL`.  
  
> [!IMPORTANT]
>  Olması durumunda olun `format` kullanıcı tanımlı bir dize sonlandırıldı null olduğundan ve doğru sayısı ve parametre türü vardır. Daha fazla bilgi için bkz: [önleme arabellek taşmasına neden](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_vsctprintf_p`|`_vscprintf_p`|`_vscprintf_p`|`_vscwprintf_p`|  
|`_vsctprintf_p_l`|`_vscprintf_p_l`|`_vscprintf_p_l`|`_vscwprintf_p_l`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_vscprintf_p`, `_vscprintf_p_l`|\<stdio.h >|  
|`_vscwprintf_p`, `_vscwprintf_p_l`|\<stdio.h > veya \<wchar.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [vsprintf](../../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [vprintf işlevleri](../../c-runtime-library/vprintf-functions.md)   
 [_scprintf_p, _scprintf_p_l, _scwprintf_p, _scwprintf_p_l](../../c-runtime-library/reference/scprintf-p-scprintf-p-l-scwprintf-p-scwprintf-p-l.md)   
 [_vscprintf, _vscprintf_l, _vscwprintf, _vscwprintf_l](../../c-runtime-library/reference/vscprintf-vscprintf-l-vscwprintf-vscwprintf-l.md)