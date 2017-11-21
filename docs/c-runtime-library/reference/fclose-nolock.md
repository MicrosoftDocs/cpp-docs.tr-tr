---
title: _fclose_nolock | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _fclose_nolock
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fclose_nolock
- _fclose_nolock
dev_langs: C++
helpviewer_keywords:
- streams, closing
- fclose_nolock function
- _fclose_nolock function
ms.assetid: b4af4392-5fc8-49bb-9fe2-ca7293d3ce04
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ec7c34187ea426688419b7171ea0c22333a1f1a9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="fclosenolock"></a>_fclose_nolock
İş parçacığı kilitleme olmadan bir akış kapatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _fclose_nolock(   
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `stream`  
 İşaretçi `FILE` yapısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `fclose`Akış başarıyla kapalıysa 0 döndürür. Döndürür `EOF` hatayı belirtmek için.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlevler kilitleme olmayan bir sürümü olan `fclose`. Girişime diğer iş parçacıkları tarafından korunmuyor dışında aynı değildir. Başka bir iş parçacığı kilitleme yükünü artırmak değil olduğundan daha hızlı olabilir. Tek iş parçacıklı uygulamalar veya arama kapsamı zaten iş parçacığı yalıtım işler burada gibi iş parçacığı bağlamlarda yalnızca bu işlevi kullanın.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|  
|--------------|---------------------|  
|`_fclose_nolock`|\<stdio.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../../c-runtime-library/stream-i-o.md)   
 [_close](../../c-runtime-library/reference/close.md)   
 [_fdopen, _wfdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)   
 [fflush](../../c-runtime-library/reference/fflush.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen, _wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)