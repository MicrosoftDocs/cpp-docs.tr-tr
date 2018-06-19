---
title: _pgmptr, _wpgmptr | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- pgmptr
- _pgmptr
- wpgmptr
- _wpgmptr
dev_langs:
- C++
helpviewer_keywords:
- wpgmptr function
- _wpgmptr function
- _pgmptr function
- pgmptr function
ms.assetid: 4d44b515-0eff-4136-8bc4-684195f218f5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5c0e944e57125def89d41010a9e76cd28bae5286
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32390004"
---
# <a name="pgmptr-wpgmptr"></a>_pgmptr, _wpgmptr
Yürütülebilir dosya yolu. Kullanım dışı; kullanmak [_get_pgmptr](../c-runtime-library/reference/get-pgmptr.md) ve [_get_wpgmptr](../c-runtime-library/reference/get-wpgmptr.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
extern char *_pgmptr;  
extern wchar_t *_wpgmptr;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Komut yorumlayıcı (Cmd.exe), bir program çalıştırıldığında `_pgmptr` yürütülebilir dosyanın tam yolunu otomatik olarak başlatılır. Hello.exe C:\BIN ve C:\BIN Örneğin, yol ise `_pgmptr` yürüttüğünüzde C:\BIN\Hello.exe için ayarlanır:  
  
```  
C> hello   
```  
  
 Bir program komut satırından değil çalıştırıldığında `_pgmptr` program adı (dosya adı uzantısı olmadan dosya temel adı) veya bir dosya adı, göreli bir yol veya tam yolunu başlatılmamış.  
  
 `_wpgmptr` joker karakter karşılık gelen biri olan `_pgmptr` ile kullanılmak üzere kullanan programlar `wmain`.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tpgmptr`|`_pgmptr`|`_pgmptr`|`_wpgmptr`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Değişken|Gerekli başlık|  
|--------------|---------------------|  
|`_pgmptr`, `_wpgmptr`|\<stdlib.h >|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki programı kullanımını gösteren `_pgmptr`.  
  
```  
// crt_pgmptr.c  
// compile with: /W3  
// The following program demonstrates the use of _pgmptr.  
//  
#include <stdio.h>  
#include <stdlib.h>  
int main( void )  
{  
   printf("The full path of the executing program is : %Fs\n",   
     _pgmptr); // C4996  
   // Note: _pgmptr is deprecated; use _get_pgmptr instead  
}  
```  
  
 Kullanabileceğinizi `_wpgmptr` değiştirerek `%Fs` için `%S` ve `main` için `wmain`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Global Değişkenler](../c-runtime-library/global-variables.md)