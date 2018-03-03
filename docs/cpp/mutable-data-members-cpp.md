---
title: "Değişebilir veri üyeleri (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- mutable_cpp
dev_langs:
- C++
helpviewer_keywords:
- mutable keyword [C++]
ms.assetid: ebe89746-3d36-43a8-8d69-f426af23f551
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a93ae14e6f630d8974163ce8295626a524b49e3c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mutable-data-members-c"></a>Değişebilir Veri Üyeleri (C++)
Bu anahtar sözcüğü yalnızca statik olmayan ve const olmayan verileri bir sınıf üyelerine uygulanabilir. Bir veri üyesi bildirilirse `mutable`, bu veri üyesi için bir değer atamak için yasal ise bir **const** üye işlevi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
mutable member-variable-declaration;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Örneğin, aşağıdaki kod hatasız olduğundan derlenir `m_accessCount` olarak bildirilen `mutable`ve bu nedenle tarafından değiştirilebilir `GetFlag` olsa bile `GetFlag` const bir üye işlevdir.  
  
```  
// mutable.cpp  
class X  
{  
public:  
   bool GetFlag() const  
   {  
      m_accessCount++;  
      return m_flag;  
   }  
private:  
   bool m_flag;  
   mutable int m_accessCount;  
};  
  
int main()  
{  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)