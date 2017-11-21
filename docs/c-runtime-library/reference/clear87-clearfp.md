---
title: _clear87, _clearfp | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _clearfp
- _clear87
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
- clearfp
- _clearfp
- _clear87
- clear87
dev_langs: C++
helpviewer_keywords:
- clearing floating point status word
- clearfp function
- _clear87 function
- _clearfp function
- clear87 function
ms.assetid: 72d24a70-7688-4793-ae09-c96d33fcca52
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 674ea06964fe245db863763169fe7b900b89cc84
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="clear87-clearfp"></a>_clear87, _clearfp
Alır ve kayan nokta durum sözcüğünü temizler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unsigned int _clear87( void );  
unsigned int _clearfp( void );  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Kayan nokta durum çağırmadan önce döndürülen değer bitleri belirtmek `_clear87` veya `_clearfp`. Tarafından döndürülen bit eksiksiz bir açıklaması için `_clear87`, Float.h bakın. Matematik kitaplık işlevleri çoğunu 8087/80287 durum word öngörülemeyen sonuçlara ile değiştirin. Değerlerin `_clear87` ve `_status87` daha az kayan nokta işlemleri kayan nokta durum sözcüğünü bilinen durumlar arasında gerçekleştirilir gibi daha güvenilir hale gelir.  
  
## <a name="remarks"></a>Açıklamalar  
 `_clear87` İşlevi kayan nokta durum sözcüğünü özel durumu bayrakları temizler, meşgul bit 0 olarak ayarlar ve durum sözcüğünü döndürür. Kayan nokta durum sözcüğünü 8087/80287 durum sözcüğünü ve kayan nokta yığın taşması ve underflow gibi 8087/80287 özel durum işleyici tarafından algılanan diğer koşullar birleşimidir.  
  
 `_clearfp`Bir platformdan bağımsız, taşınabilir sürümü `_clear87` yordamı. Aynı `_clear87` Intel (x86) platformlarda ve ayrıca x64 ve ARM platformlar tarafından desteklenir. Kayan nokta kodunuzu x64 ve ARM taşınabilir olduğundan emin olmak için kullanmak `_clearfp`. X86 yalnızca hedefliyorsanız platformları, kullanabilirsiniz `_clear87` veya `_clearfp`.  
  
 Bu işlevler ile derleme yapılırken bırakılmıştır [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) çünkü ortak dil çalışma zamanı yalnızca varsayılan kayan nokta duyarlık destekler.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_clear87`|\<float.h >|  
|`_clearfp`|\<float.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_clear87.c  
// compile with: /Od  
  
// This program creates various floating-point   
// problems, then uses _clear87 to report on these problems.  
// Compile this program with Optimizations disabled (/Od).   
// Otherwise the optimizer will remove the code associated with   
// the unused floating-point values.  
//  
  
#include <stdio.h>  
#include <float.h>  
  
int main( void )  
{  
   double a = 1e-40, b;  
   float x, y;  
  
   printf( "Status: %.4x - clear\n", _clear87()  );  
  
   // Store into y is inexact and underflows:  
   y = a;  
   printf( "Status: %.4x - inexact, underflow\n", _clear87() );  
  
   // y is denormal:   
   b = y;  
   printf( "Status: %.4x - denormal\n", _clear87() );  
}  
```  
  
```Output  
Status: 0000 - clear  
Status: 0003 - inexact, underflow  
Status: 80000 - denormal  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)   
 [_status87, _statusfp, _statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)