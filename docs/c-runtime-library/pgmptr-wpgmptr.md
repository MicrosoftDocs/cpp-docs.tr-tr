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
ms.workload: cplusplus
ms.openlocfilehash: e8bf941f5e020a608817919b2819f2d6be023d89
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [Global Değişkenler](../c-runtime-library/global-variables.md)