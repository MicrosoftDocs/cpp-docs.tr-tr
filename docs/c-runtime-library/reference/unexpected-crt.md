---
title: Beklenmeyen (CRT) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: unexpected
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
f1_keywords: unexpected
dev_langs: C++
helpviewer_keywords: unexpected function
ms.assetid: 2f873763-15ad-4556-a924-dcf28f2b52b4
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 39cc7164a22b95f2c269c7bb1bd558374f56fa3c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="unexpected-crt"></a>beklenmeyen (CRT)
Çağrıları `terminate` veya kullanarak belirttiğiniz işlevi `set_unexpected`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void unexpected( void );  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `unexpected` Yordamı C++ özel durum işleme geçerli uygulamasıyla kullanılmaz. `unexpected`çağrıları `terminate` varsayılan olarak. Özel sonlandırma işlevi yazma ve arama bu varsayılan davranışı değiştirebilirsiniz `set_unexpected` işlevinizi bağımsız değişkeni olarak adı. `unexpected`bağımsız değişken olarak verilen son işlevi çağırır `set_unexpected`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`unexpected`|\<EH.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel durum işleme rutinleri](../../c-runtime-library/exception-handling-routines.md)   
 [durdurma](../../c-runtime-library/reference/abort.md)   
 [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md)   
 [set_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [set_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [sonlandırma](../../c-runtime-library/reference/terminate-crt.md)