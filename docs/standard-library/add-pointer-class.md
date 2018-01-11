---
title: "add_pointer sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::add_pointer
dev_langs: C++
helpviewer_keywords:
- add_pointer class
- add_pointer
ms.assetid: d8095cb0-6578-4143-b78f-87f82485298c
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2a7af4a099d06b98ceb5fdd4bfb6dca0071c3f4a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="addpointer-class"></a>add_pointer Sınıfı
Belirtilen türden bir işaretçi türü sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <class T>  
struct add_pointer;  
 
template <class T>
using add_pointer_t = typename add_pointer<T>::type;  
```  
  
#### <a name="parameters"></a>Parametreler  
*T*  
Değiştirilecek tür.  
  
## <a name="remarks"></a>Açıklamalar  
Üye typedef `type` aynı türde adları `remove_reference<T>::type*`. Diğer ad `add_pointer_t` üye typedef erişmek için bir kısayol `type`.  
  
Bir işaretçi bir başvuru yapmak için geçersiz olduğundan `add_pointer` başvuru varsa kaldırır, kendisinden önce belirtilen türden işaretçi-için-type hale getirir. Sonuç olarak, bir türü ile kullanabileceğiniz `add_pointer` türü bir başvuru olup hakkında kaygı olmadan.  
  
## <a name="example"></a>Örnek  
Aşağıdaki örnekte gösterilmiştir `add_pointer` türü türü için bir işaretçi ile aynıdır.  
  
```cpp  
#include <type_traits>   
#include <iostream>   
  
int main()   
{   
    std::add_pointer_t<int> *p = (int **)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "add_pointer_t<int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
add_pointer_t<int> == int *  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<type_traits >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [< type_traits >](../standard-library/type-traits.md)   
 [remove_pointer Sınıfı](../standard-library/remove-pointer-class.md)
