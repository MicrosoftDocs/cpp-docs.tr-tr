---
title: __ud2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __ud2
dev_langs: C++
helpviewer_keywords:
- UD2 instruction
- __ud2 intrinsic
ms.assetid: 0831cd5a-8b65-402e-bb57-11e1d5d7ffd2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 699e575d283f830d94c123f7748f7fdaa6272ff5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ud2"></a>__ud2
**Microsoft özel**  
  
 Tanımlanmamış bir yönerge oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void __ud2();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Tanımlanmamış bir yönerge yürütüyorsa işlemci geçersiz opcode özel durumu tetikler.  
  
 `__ud2` İşlevi eşdeğerdir `UD2` makine yönerge ve yalnızca çekirdek modunda kullanılabilir. Daha fazla bilgi için belge için arama "Intel mimarisi yazılım geliştirici el ile 2 birimi: yönerge kümesi başvurusu" konumundaki [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) site.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__ud2`|x86,[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
**SON Microsoft özel**  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir özel durum oluşturur tanımlanmamış bir yönerge yürütür. Özel durum işleyici dönüş kodu bir sıfırdan sonra değiştirir.  
  
```  
// __ud2_intrinsic.cpp  
#include <stdio.h>  
#include <intrin.h>  
#include <excpt.h>  
// compile with /EHa  
  
int main() {  
  
// Initialize the return code to 0.  
 int ret = 0;  
  
// Attempt to execute an undefined instruction.  
  printf("Before __ud2(). Return code = %d.\n", ret);  
  __try {   
  __ud2();   
  }  
  
// Catch any exceptions and set the return code to 1.  
  __except(EXCEPTION_EXECUTE_HANDLER){  
  printf("  In the exception handler.\n");  
  ret = 1;  
  }  
  
// Report the value of the return code.   
  printf("After __ud2().  Return code = %d.\n", ret);  
  return ret;  
}  
```  
  
```Output  
Before __ud2(). Return code = 0.  
  In the exception handler.  
After __ud2().  Return code = 1.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)