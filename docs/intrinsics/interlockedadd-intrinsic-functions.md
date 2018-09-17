---
title: _Interlockedadd iç işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7607083a50d98a1b531d6ea45e04866f253a7dfb
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45709533"
---
# <a name="interlockedadd-intrinsic-functions"></a>_InterlockedAdd İç İşlevleri
**Microsoft'a özgü**  
  
 Birden çok iş parçacığı paylaşılan değişkene erişimi olduğunda işlemin başarıyla tamamlanmasını sağlar bir atomik ayrıca gerçekleştirin.  
  
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
*Formülündeki toplanan*<br/>
[out içinde] Eklenecek tamsayı işaretçisi; toplamın sonucunu tarafından değiştirildi.  
  
*Değer*<br/>
[in] Eklenecek değer.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Her iki işlev de toplamın sonucunu döndürür.  
  
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
  
 **Üst bilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 Sahip bu işlevlerin sürümleri `_acq` veya `_rel` sonekleri bir birbirine kenetlenmiş ayrıca Al veya sürüm semantiği aşağıdaki gerçekleştirin. Önce herhangi bir sonraki bellek, okuma ve yazma işleminin sonucu tüm iş parçacıkları ve işlemciler görünür yapılır semantiği anlamına gelir edinin. Alma kritik bölüm girerken yararlı olur. Release semantikleri, tüm bellek okuma ve yazma işleminin sonucu kendisini görünür hale gelir önce tüm iş parçacıkları ve işlemciler için görünür duruma zorlanır anlamına gelir. Yayın, bir kritik bölüm ayrılırken yararlıdır. Yapı içleri ile bir `_nf` ("hiçbir sınır") soneki bellek önünde bir engel hareket değil.  
  
 Bu yordamlar, yalnızca iç öğe olarak kullanılabilir.  
  
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
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [x86 Derleyicisi ile Çakışma](../build/conflicts-with-the-x86-compiler.md)