---
title: "Allocator&lt;void&gt; sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- memory/std::allocator<void>
- allocator<void>
dev_langs: C++
helpviewer_keywords: allocator<void> class
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e1d9ddd5c719bffe8fec9c77c3495e7d170eaeb0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="allocatorltvoidgt-class"></a>Allocator&lt;void&gt; sınıfı
Türü için Şablon sınıfı ayırıcısı uzmanlaşması `void`, bu bağlamda anlamlı türleri tanımlama.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <>
class allocator<void> {
    typedef void *pointer;
    typedef const void *const_pointer;
    typedef void value_type;
    template <class Other>
    struct rebind;
    allocator();
    allocator(const allocator<void>&);

    template <class Other>
    allocator(const allocator<Other>&);

    template <class Other>
    allocator<void>& operator=(const allocator<Other>&);
};
```  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıf şablonu sınıfı açıkça uzmanlaşmış [ayırıcısı](../standard-library/allocator-class.md) türü için *void.* Oluşturucular ve atama işleci Şablon sınıfı için olduğu gibi aynı şekilde davranır, ancak yalnızca şu türleri tanımlar:  
  
- [const_pointer](../standard-library/allocator-class.md#const_pointer).  
  
- [İşaretçi](../standard-library/allocator-class.md#pointer).  
  
- [value_type](../standard-library/allocator-class.md#value_type).  
  
- [rebind](../standard-library/allocator-class.md#rebind), bir şablon sınıfı iç içe geçmiş.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<bellek >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)



