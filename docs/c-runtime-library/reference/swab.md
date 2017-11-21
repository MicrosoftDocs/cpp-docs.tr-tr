---
title: _swab | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _swab
- stdlib/_swab
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
- _swab
- stdlib/_swab
dev_langs: C++
helpviewer_keywords:
- _swab function
- swapping bytes
- swab function
- bytes, swapping
ms.assetid: 017142f2-050c-4f6a-8b49-6b094f58ec94
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a3043abf425055d8cb21108a30db2e6382e19c1a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="swab"></a>_swab
Bayt değiştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void _swab(  
   char *src,  
   char *dest,  
   int n   
);  
```  
  
## <a name="parameters"></a>Parametreler  
 `src`  
 Kopyalanır ve takas için veri.  
  
 `dest`  
 Değiştirilen verileri için depolama konumu.  
  
 `n`  
 Kopyalanan ve takas bayt sayısı.  
  
## <a name="return-value"></a>Dönüş değeri
 `swab` İşlevi bir değer döndürmez. İşlev kümeleri `errno` için `EINVAL` her iki `src` veya `dest` işaretçidir null veya `n` küçük sıfır ve geçersiz bir parametre işleyici, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md).  
  
 Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer dönüş kodları hakkında daha fazla bilgi için.
 
## <a name="remarks"></a>Açıklamalar  
 Varsa `n` olsa bile, `_swab` işlev kopyaları `n` baytlar `src`her çifti bitişik bayt değiştirir ve sonucunda depolar `dest`. Varsa `n` tek, olup `_swab` kopyalar ve ilk değiştirir `n-1` bayt `src`, ve son bayt kopyalanmaz. `_swab` İşlevi farklı bayt sırası kullanan bir makine aktarmak için ikili verileri hazırlamak için genellikle kullanılır.  
  
## <a name="requirements"></a>Gereksinimler  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_swab`|C: \<stdlib.h > C++: \<cstdlib > veya \<stdlib.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
```C 
// crt_swab.c  
  
#include <stdlib.h>  
#include <stdio.h>  
  
char from[] = "BADCFEHGJILKNMPORQTSVUXWZY";  
char to[] =   "...........................";  
  
int main()  
{  
    printf("Before: %s  %d bytes\n        %s\n\n", from, sizeof(from), to);  
    _swab(from, to, sizeof(from));  
    printf("After:  %s\n        %s\n\n", from, to);  
}  
```  
  
```Output  
Before: BADCFEHGJILKNMPORQTSVUXWZY  27 bytes  
        ...........................  
  
After:  BADCFEHGJILKNMPORQTSVUXWZY  
        ABCDEFGHIJKLMNOPQRSTUVWXYZ.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ara bellek düzenlemesi](../../c-runtime-library/buffer-manipulation.md)