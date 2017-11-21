---
title: _pgmptr, _wpgmptr | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- pgmptr
- _pgmptr
- wpgmptr
- _wpgmptr
dev_langs: C++
helpviewer_keywords:
- wpgmptr function
- _wpgmptr function
- _pgmptr function
- pgmptr function
ms.assetid: 4d44b515-0eff-4136-8bc4-684195f218f5
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 21d3ad8d4cbd73c2a1ab99497db2f671196de523
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
  
 `_wpgmptr`joker karakter karşılık gelen biri olan `_pgmptr` ile kullanılmak üzere kullanan programlar `wmain`.  
  
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
 [Genel değişkenler](../c-runtime-library/global-variables.md)