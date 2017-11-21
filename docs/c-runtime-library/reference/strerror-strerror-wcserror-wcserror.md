---
title: strerror, _strerror, _wcserror, __wcserror | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- strerror
- _strerror
- _wcserror
- __wcserror
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- __sys_errlist
- wcserror
- _strerror
- __wcserror
- strerror
- __sys_nerr
- _tcserror
- _wcserror
- tcserror
dev_langs: C++
helpviewer_keywords:
- strerror function
- _strerror function
- __sys_errlist
- wcserror function
- error messages, printing
- __sys_nerr
- tcserror function
- printing error messages
- _wcserror function
- _tcserror function
- __wcserror function
- error messages, getting
ms.assetid: 27b72255-f627-43c0-8836-bcda8b003e14
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b534c0a43c78c42265fa3b36aca523dc27e170fd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="strerror-strerror-wcserror-wcserror"></a>strerror, _strerror, _wcserror, __wcserror
Bir sistem hata ileti dizesi alır (`strerror`, `_wcserror`) veya bir kullanıcı tarafından sağlanan hata ileti dizesi biçimleri (`_strerror`, `__wcserror`). Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [strerror_s, _strerror_s, _wcserror_s, \__wcserror_s](../../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
char *strerror(  
   int errnum   
);  
char *_strerror(  
   const char *strErrMsg   
);  
wchar_t * _wcserror(  
   int errnum   
);  
wchar_t * __wcserror(  
   const wchar_t *strErrMsg   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `errnum`  
 Hata numarası.  
  
 `strErrMsg`  
 Kullanıcı tarafından sağlanan ileti.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Tüm bu işlevlerin bir işaretçi hata iletisi dizesi olarak döndürür. Sonraki çağrılar dize üzerine yazabilirsiniz.  
  
## <a name="remarks"></a>Açıklamalar  
 `strerror` İşlev eşlemeleri `errnum` bir hata iletisi dizesi ve bir işaretçi dizesi olarak döndürür. Ne `strerror` ya da `_strerror` gerçekten ileti yazdırır: gibi bir çıktı işlevi çağırmak, için sahip [fprintf](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md):  
  
```  
if (( _access( "datafile",2 )) == -1 )  
   fprintf( stderr, _strerror(NULL) );  
```  
  
 Varsa `strErrMsg` olarak geçirilen `NULL`, `_strerror` bir işaretçi bir hata üretilen son kitaplığı çağrı için sistem hata iletisini içeren bir dize döndürür. Hata ileti dizesi yeni satır karakteri ('\n') tarafından sonlandırıldı. Varsa `strErrMsg` eşit değil `NULL`, ardından `_strerror` bir işaretçi (sırasıyla) dize iletinizi, iki nokta, bir boşluk, bir hata ve yeni satır karakteri üretir son kitaplığı çağrı için sistem hata iletisini içeren bir dize döndürür. Dize ileti en fazla 94 karakterden uzun olamaz.  
  
 Gerçek hata numarası `_strerror` değişkeninde depolanan [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Doğru sonuçlar üretmek için çağrı `_strerror` hemen bir hata ile kitaplığı yordamı döndükten sonra. Aksi takdirde, sonraki çağrılar `strerror` veya `_strerror` kılabilirsiniz `errno` değeri.  
  
 `_wcserror`ve `__wcserror` joker karakter sürümleri `strerror` ve `_strerror`sırasıyla.  
  
 `_strerror`, `_wcserror`, ve `__wcserror` ANSI tanımının bir parçası değildir; Microsoft uzantıları ve, bunları taşınabilir kod istediğiniz kullanmamanızı öneririz. ANSI uyumluluğu için kullanmanız `strerror` yerine.  
  
 Hata dizeleri almak için öneririz `strerror` veya `_wcserror` kullanım dışı makroları yerine [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) ve [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) ve kullanım dışı iç işlevleri `__sys_errlist` ve `__sys_nerr`.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcserror`|`strerror`|`strerror`|`_wcserror`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`strerror`|\<String.h >|  
|`_strerror`|\<String.h >|  
|`_wcserror`, `__wcserror`|\<String.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [perror](../../c-runtime-library/reference/perror-wperror.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror, _wperror](../../c-runtime-library/reference/perror-wperror.md)