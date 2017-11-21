---
title: "is_pod sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_pod
dev_langs: C++
helpviewer_keywords:
- is_pod class
- is_pod
ms.assetid: d73ebdee-746b-4082-9fa4-2db71432eb0e
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 67341c89d480f6ef0d44415f65dd0cd37bb065fb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ispod-class"></a>is_pod Sınıfı
Testleri POD türüdür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T>
struct is_pod;
```  
  
#### <a name="parameters"></a>Parametreler  
*T*  
Sorgulanacak tür.  
  
## <a name="remarks"></a>Açıklamalar  
`is_pod<T>::value`olan `true` varsa türü *T* düz eski verileri (POD) değil. Aksi takdirde değer `false`.  
  
Aritmetik türleri, numaralandırma türleri, işaretçi türleri ve üye türleri işaretçisine POD ' dir.  
  
POD türü MS tam sürümü kendisini bir POD türüdür.  
  
POD kendisini POD dizisidir.  
  
Bu yapı ya da statik olmayan veri üyeleri POD tümü, UNION, kendisini POD ise:  
  
-   Kullanıcı bildirilen oluşturucu yok.  
  
-   Statik olmayan verileri özel veya korumalı üye yok.  
  
-   Temel olmayan sınıflar.  
  
-   Sanal işlevler yok.  
  
-   Başvuru türü statik olmayan veri üye yok.  
  
-   Hiçbir kullanıcı tarafından tanımlanan kopya atama işleci.  
  
-   Hiçbir kullanıcı tarafından tanımlanan yıkıcı.  
  
Bu nedenle, yinelemeli olarak yapı POD yapılar ve POD yapıları ve diziler içeren dizileri kullanabilirsiniz.  
  
## <a name="example"></a>Örnek  
  
```cpp  
// std__type_traits__is_pod.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial {   
    int val;   
};   
  
struct throws {   
    throws() {}  // User-declared ctor, so not POD
  
    int val;   
};   
  
int main() {   
    std::cout << "is_pod<trivial> == " << std::boolalpha   
        << std::is_pod<trivial>::value << std::endl;   
    std::cout << "is_pod<int> == " << std::boolalpha   
        << std::is_pod<int>::value << std::endl;   
    std::cout << "is_pod<throws> == " << std::boolalpha   
        << std::is_pod<throws>::value << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
is_pod<trivial> == true  
is_pod<int> == true  
is_pod<throws> == false  
```  
  
## <a name="requirements"></a>Gereksinimler  
**Başlık:** \<type_traits >  
  
**Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[< type_traits >](../standard-library/type-traits.md)



