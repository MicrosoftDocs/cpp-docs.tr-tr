---
title: _putch_nolock, _putwch_nolock | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _putwch_nolock
- _putch_nolock
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
- api-ms-win-crt-conio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _putch_nolock
- _puttch_nolock
- putch_nolock
- putwch_nolock
- _putwch_nolock
dev_langs:
- C++
helpviewer_keywords:
- putwch_nolock function
- puttch_nolock function
- characters, writing
- putch_nolock function
- _putch_nolock function
- _puttch_nolock function
- console, writing characters to
- _putwch_nolock function
ms.assetid: edbc811d-bac6-47fa-a872-fe4f3a1590b0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 13db2622b7dd9829b744a0164fbb0a025f4013ae
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="putchnolock-putwchnolock"></a>_putch_nolock, _putwch_nolock
Bir karakter, iş parçacığı kilitlemeden konsola yazar.  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      int _putch_nolock(  
int c  
);  
wint_t _putwch_nolock(  
wchar_t c  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *c*  
 Çıktı karakter.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Döndürür *c* başarılı olursa. Varsa **_putch_nolock** başarısız, döndürdüğü **EOF**if **_putwch_nolock** başarısız, onu döndürür **WEOF**.  
  
## <a name="remarks"></a>Açıklamalar  
 **_putch_nolock** ve **_putwch_nolock** özdeş **_putch** ve **_putwch**, sırasıyla girişim tarafından gelen korunmayan dışında diğer iş parçacığı sayısı. Bunlar başka bir iş parçacığı kilitleme zahmetine değil olduğundan daha hızlı olabilir. Bu işlevler yalnızca iş parçacığı bağlamları tek iş parçacıklı uygulamalar veya arama kapsamı zaten iş parçacığı yalıtım işleme olduğu gibi kullanın.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|**_puttch_nolock**|**_putch_nolock**|**_putch_nolock**|**_putwch_nolock**|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|**_putch_nolock**|\<conio.h >|  
|**_putwch_nolock**|\<conio.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Konsol ve bağlantı noktası g/ç](../../c-runtime-library/console-and-port-i-o.md)   
 [_cprintf, _cprintf_l, _cwprintf, _cwprintf_l](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)   
 [_getch, _getwch](../../c-runtime-library/reference/getch-getwch.md)