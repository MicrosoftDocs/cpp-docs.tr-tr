---
title: _set_output_format | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _set_output_format
apilocation:
- msvcrt.dll
- msvcr120.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr110.dll
- msvcr80.dll
apitype: DLLExport
f1_keywords:
- set_output_format
- _set_output_format
dev_langs: C++
helpviewer_keywords:
- _TWO_DIGIT_EXPONENT constant
- output formatting
- TWO_DIGIT_EXPONENT constant
- _set_output_format function
- set_output_format function
ms.assetid: 1cb48df8-44b4-4400-bd27-287831d6b3ff
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4a0ad6631d9171e8fcdc59e13e60eda2cc729c79
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="setoutputformat"></a>_set_output_format
Biçimlendirilmiş g/ç işlevleri tarafından kullanılan çıkış biçimlerini özelleştirir.  
  
> [!IMPORTANT]
>  Bu işlev artık kullanılmıyor. Visual Studio 2015'te başlayarak, CRT kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unsigned int _set_output_format(  
   unsigned int format  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in]`format`  
 Kullanılacak biçim temsil eden bir değer.  
  
## <a name="return-value"></a>Dönüş değeri  
 Önceki çıktı biçimi.  
  
## <a name="remarks"></a>Açıklamalar  
 `_set_output_format`biçimlendirilmiş g/ç işlevleri çıktısı gibi yapılandırmak için kullanılan [printf_s](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md). Şu anda bu işlev tarafından değiştirilebilen tek biçimlendirme kayan nokta numarası çıktı üstel görüntülenen basamak sayısı kuraldır.  
  
 Varsayılan olarak, kayan çıkış noktası numaralarını işlevleri tarafından gibi `printf_s`, `wprintf_s`, ve ilgili işlevleri Visual C++ Standart C Kitaplığı'nda üç basamak değerini temsil eden için gerekli olsa bile bu üç basamak üs yazdırır Üs. Sıfır üç basamak değerine paneli için kullanılır. `_set_output_format`Böylece üçüncü basamak üs boyutu tarafından gerekli olmadıkça yalnızca iki basamak üs olarak yazdırılır bu davranışı değiştirmenize izin verir.  
  
 İki basamaklı üs etkinleştirmek için bu işlev parametresi ile çağırın `_TWO_DIGIT_EXPONENT`, örnekte gösterildiği gibi. İki basamaklı üs devre dışı bırakmak için bu işlev bağımsız değişkeni 0 çağırın.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_set_output_format`|\<stdio.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```C  
// crt_set_output_format.c  
#include <stdio.h>  
  
void printvalues(double x, double y)  
{  
   printf_s("%11.4e %11.4e\n", x, y);  
   printf_s("%11.4E %11.4E\n", x, y);  
   printf_s("%11.4g %11.4g\n", x, y);  
   printf_s("%11.4G %11.4G\n", x, y);  
}  
  
int main()  
{  
   double x = 1.211E-5;  
   double y = 2.3056E-112;  
   unsigned int old_exponent_format;  
  
   // Use the default format  
   printvalues(x, y);  
  
   // Enable two-digit exponent format  
   old_exponent_format = _set_output_format(_TWO_DIGIT_EXPONENT);  
  
   printvalues(x, y);  
  
   // Disable two-digit exponent format  
   _set_output_format( old_exponent_format );  
  
   printvalues(x, y);  
}  
```  
  
```Output  
1.2110e-005 2.3056e-112  
1.2110E-005 2.3056E-112  
 1.211e-005  2.306e-112  
 1.211E-005  2.306E-112  
 1.2110e-05 2.3056e-112  
 1.2110E-05 2.3056E-112  
  1.211e-05  2.306e-112  
  1.211E-05  2.306E-112  
1.2110e-005 2.3056e-112  
1.2110E-005 2.3056E-112  
 1.211e-005  2.306e-112  
 1.211E-005  2.306E-112  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)   
 [_get_output_format](../c-runtime-library/get-output-format.md)