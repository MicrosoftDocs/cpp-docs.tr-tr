---
title: "_Interlockedadd iç işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _InterlockedAdd64_acq_cpp
- _InterlockedAdd64_acq
- _InterlockedAdd_acq
- _InterlockedAdd_nf
- _InterlockedAdd64_rel
- _InterlockedAdd64
- _InterlockedAdd_cpp
- _InterlockedAdd_rel_cpp
- _InterlockedAdd_rel
- _InterlockedAdd64_rel_cpp
- _InterlockedAdd64_cpp
- _InterlockedAdd_acq_cpp
- _InterlockedAdd64_nf
- _InterlockedAdd
dev_langs: C++
helpviewer_keywords:
- _InterlockedAdd_nf intrinsic
- _InterlockedAdd_rel intrinsic
- _InterlockedAdd intrinsic
- _InterlockedAdd64 intrinsic
- _InterlockedAdd64_acq intrinsic
- _InterlockedAdd64_nf intrinsic
- _InterlockedAdd_acq intrinsic
- _InterlockedAdd64_rel intrinsic
ms.assetid: 3d319603-ea9c-4fdd-ae61-e52430ccc3b1
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f07115db4d627a1116f9eaefd0f1731841be83ab
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="interlockedadd-intrinsic-functions"></a>_InterlockedAdd İç İşlevleri
**Microsoft özel**  
  
 Birden çok iş parçacığı bir paylaşılan değişken erişimi olduğunda işlemi başarıyla tamamlandıktan sağlayan bir atomik eklenmesini gerçekleştirme.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
long _InterlockedAdd(  
   long volatile * Addend,  
   long Value  
);  
long _InterlockedAdd_acq(  
   long volatile * Addend,  
   long Value  
);  
long _InterlockedAdd_nf(  
   long volatile * Addend,  
   long Value  
);  
long _InterlockedAdd_rel(  
   long volatile * Addend,  
   long Value  
);  
__int64 _InterlockedAdd64(  
   __int64 volatile * Addend,  
   __int64 Value  
);  
__int64 _InterlockedAdd64_acq(  
   __int64 volatile * Addend,  
   __int64 Value  
);  
__int64 _InterlockedAdd64_nf (  
   __int64 volatile * Addend,  
   __int64 Value  
);  
__int64 _InterlockedAdd64_rel(  
   __int64 volatile * Addend,  
   __int64 Value  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [içinde out]`Addend`  
 İşaretçi eklenecek tamsayıya; ek sonuç tarafından değiştirildi.  
  
 [in]`Value`  
 Eklenecek değer.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Her iki işlevler toplamın sonucunu döndürür.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`_InterlockedAdd`|ARM|  
|`_InterlockedAdd_acq`|ARM|  
|`_InterlockedAdd_nf`|ARM|  
|`_InterlockedAdd_rel`|ARM|  
|`_InterlockedAdd64`|ARM|  
|`_InterlockedAdd64_acq`|ARM|  
|`_InterlockedAdd64_nf`|ARM|  
|`_InterlockedAdd64_rel`|ARM|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlevleri sürümlerini `_acq` veya `_rel` sonekleri edinme veya yayın semantiği aşağıdaki ınterlocked ek gerçekleştirin. Alma işleminin sonucu yapılan tüm iş parçacıkları ve işlemci görünür sonraki belleği okuyan ve yazan önce semantiği anlamına gelir. Alma önemli bir bölümü girerken yararlıdır. Yayın semantiği tüm bellek okuma ve yazma işlemleri işlemin sonucunu kendisini görünür hale gelir önce tüm iş parçacıkları ve işlemci görünür duruma getirilmek üzere zorlanır anlamına gelir. Yayın önemli bir bölümü ayrılırken yararlıdır. İç bilgiler ile bir `_nf` ("hiçbir dilimi") soneki bir bellek engeli hareket değil.  
  
 Bu yordamlar, yalnızca iç bilgileri kullanılabilir.  
  
## <a name="example"></a>Örnek  
  
```  
// interlockedadd.cpp  
// Compile with: /Oi /EHsc  
// processor: ARM  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_InterlockedAdd)  
  
int main()  
{  
        long data1 = 0xFF00FF00;  
        long data2 = 0x00FF0000;  
        long retval;  
        retval = _InterlockedAdd(&data1, data2);  
        printf("0x%x 0x%x 0x%x", data1, data2, retval);  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```  
0xffffff00 0xff0000 0xffffff00  
```  
  
## <a name="example"></a>Örnek  
  
```  
// interlockedadd64.cpp  
// compile with: /Oi /EHsc  
// processor: ARM  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(_InterlockedAdd64)  
  
int main()  
{  
        __int64 data1 = 0x0000FF0000000000;  
        __int64 data2 = 0x00FF0000FFFFFFFF;  
        __int64 retval;  
        cout << hex << data1 << " + " << data2 << " = " ;  
        retval = _InterlockedAdd64(&data1, data2);  
        cout << data1 << endl;  
        cout << "Return value: " << retval << endl;  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```  
ff0000000000 + ff0000ffffffff = ffff00ffffffff  
Return value: ffff00ffffffff  
```  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [X86 çakışıyor derleyici](../build/conflicts-with-the-x86-compiler.md)