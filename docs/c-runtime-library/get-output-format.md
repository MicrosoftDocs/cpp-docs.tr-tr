---
title: _get_output_format | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _get_output_format
apilocation:
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr80.dll
- msvcrt.dll
- msvcr90.dll
- msvcr120.dll
- msvcr110.dll
apitype: DLLExport
f1_keywords:
- get_output_format
- _get_output_format
dev_langs:
- C++
helpviewer_keywords:
- output formatting
- get_output_format function
- _get_output_format function
ms.assetid: 0ce42f3b-3479-41c4-bcbf-1d21f7ee37e7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 30ee8de9c39d2b7e1fc6f9cf0a717120c95e92c0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="getoutputformat"></a>_get_output_format
Çıktı biçimi bayrağı geçerli değerini alır.  
  
> [!IMPORTANT]
>  Bu işlev artık kullanılmıyor. Visual Studio 2015'te başlayarak, CRT kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unsigned int _get_output_format();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Çıktı biçimi bayrağı geçerli değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 Çıktı biçimi bayrağı biçimlendirilmiş g/ç özelliklerini denetler. Şu anda bayrağı iki olası değerler vardır: 0 ve `_TWO_DIGIT_EXPONENT`. Varsa `_TWO_DIGIT_EXPONENT` ayarlanır kayan nokta numaraları yazdırılan üs yalnızca iki basamak ile üçüncü basamak üs boyutu tarafından gerekli olmadıkça. Kayan nokta bayrağı sıfırsa çıktısını görüntüler üç sıfır üç basamak değerine doldurulacak gerekirse kullanarak üs rakamı.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_get_output_format`|\<stdio.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../c-runtime-library/compatibility.md) giriş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[Biçim Belirtim Sözdizimi: printf ve wprintf İşlevleri](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)  
 [Printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)   
 [_set_output_format](../c-runtime-library/set-output-format.md)  
