---
title: _get_printf_count_output | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _get_printf_count_output
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
- get_printf_count_output
- _get_printf_count_output
dev_langs: C++
helpviewer_keywords:
- '%n format'
- get_printf_count_output function
- _get_printf_count_output function
ms.assetid: 850f9f33-8319-433e-98d8-6a694200d994
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 78c48423be0bc642b96c7a46d75f101e183c73fe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="getprintfcountoutput"></a>_get_printf_count_output
Gösterir olup olmadığını [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)-ailesi işlevleri Destek `%n` biçimi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _get_printf_count_output();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Sıfır dışı IF `%n` desteklenir, 0 ise `%n` desteklenmiyor.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa `%n` olduğunu (varsayılan), desteklenmeyen karşılaşmadan `%n` herhangi bir dize biçiminde `printf` açıklandığı gibi işlevleri geçersiz parametre işleyicisi çağırılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Varsa `%n` desteği etkin (bkz [_set_printf_count_output](../../c-runtime-library/reference/set-printf-count-output.md)) sonra `%n` açıklandığı gibi davranacak [biçim belirtim Sözdizimi: printf ve wprintf işlevleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_get_printf_count_output`|\<stdio.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [_set_printf_count_output](../../c-runtime-library/reference/set-printf-count-output.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[_set_printf_count_output](../../c-runtime-library/reference/set-printf-count-output.md)  
