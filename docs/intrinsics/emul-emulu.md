---
title: __emul, __emulu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __emulu_cpp
- __emul
- __emul_cpp
- __emulu
dev_langs:
- C++
helpviewer_keywords:
- __emul intrinsic
- __emulu intrinsic
ms.assetid: 79545236-cca2-40b8-a4e1-8abce9b26311
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f3bf997006d98cfbd05a47140baf53ef7032876
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45719426"
---
# <a name="emul-emulu"></a>__emul, __emulu
**Microsoft'a özgü**  
  
 Bir 32 bit tamsayı basılı tutabilirsiniz overflow multiplications gerçekleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
__int64 __emul(  
   int a,  
   int b  
);  
unsigned __int64 __emulu(  
   unsigned int a,  
   unsigned int b  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
*a*<br/>
[in] Çarpma işleminin ilk tamsayı işlenen.  
  
*b*<br/>
[in] Çarpma işleminin tamsayı ikinci işlenen.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Çarpma işleminin sonucu.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__emul`|x86, x64|  
|`__emulu`|x86, x64|  
  
 **Üst bilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 `__emul` iki 32-bit imzalı değerlerini alır ve 64-bit imzalı bir tamsayı değeri olarak çarpma işleminin sonucunu döndürür.  
  
 `__emulu` iki 32-bit işaretsiz tamsayı değerleri alır ve 64-bit işaretsiz tamsayı değeri olarak çarpma işleminin sonucunu döndürür.  
  
## <a name="example"></a>Örnek  
  
```  
// emul.cpp  
// compile with: /EHsc  
// processor: x86, x64  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(__emul)  
#pragma intrinsic(__emulu)  
  
int main()  
{  
   int a = -268435456;   
   int b = 2;   
  
   __int64 result = __emul(a, b);  
  
   cout << a << " * " << b << " = " << result << endl;  
  
   unsigned int ua = 0xFFFFFFFF; // Dec value: 4294967295  
   unsigned int ub = 0xF000000;  // Dec value: 251658240  
  
   unsigned __int64 uresult = __emulu(ua, ub);  
  
   cout << ua << " * " << ub << " = " << uresult << endl;  
  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```  
-268435456 * 2 = -536870912  
4294967295 * 251658240 = 1080863910317260800  
```  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)