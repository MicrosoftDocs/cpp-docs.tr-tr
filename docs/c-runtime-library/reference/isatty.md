---
title: _isatty | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _isatty
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
- _isatty
dev_langs:
- C++
helpviewer_keywords:
- isatty function
- character device checking
- _isatty function
- checking character devices
ms.assetid: 9f1b2e87-0cd7-4079-b187-f2b7ca15fcbe
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bea907f22496c3c1abe86462357ba14514a4aca7
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="isatty"></a>_isatty
Bir dosya tanımlayıcısı karakter aygıtla ilişkili olup olmadığını belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      int _isatty(  
int fd   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `fd`  
 Sınanacak cihaza başvuruyor dosya tanımlayıcısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `_isatty` tanımlayıcı karakter cihaz ile ilişkili ise, sıfır olmayan bir değer döndürür. Aksi takdirde `_isatty` 0 döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `_isatty` İşlevi belirler olup olmadığını `fd` bir karakter cihaza (bir terminal, konsol, yazıcı veya seri bağlantı noktası).  
  
 Bu işlev doğrular `fd` parametresi. Varsa `fd` hatalı dosya işaretçi açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için 0 işlevi döndürür ve kümelerini yürütülmesine izin veriliyorsa `errno` için `EBADF`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_isatty`|\<io.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_isatty.c  
/* This program checks to see whether  
 * stdout has been redirected to a file.  
 */  
  
#include <stdio.h>  
#include <io.h>  
  
int main( void )  
{  
   if( _isatty( _fileno( stdout ) ) )  
      printf( "stdout has not been redirected to a file\n" );  
   else  
      printf( "stdout has been redirected to a file\n");  
}  
```  
  
## <a name="sample-output"></a>Örnek Çıktı  
  
```  
stdout has not been redirected to a file  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dosya İşleme](../../c-runtime-library/file-handling.md)