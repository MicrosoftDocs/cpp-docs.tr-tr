---
title: Değişebilir veri üyeleri (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- mutable_cpp
dev_langs:
- C++
helpviewer_keywords:
- mutable keyword [C++]
ms.assetid: ebe89746-3d36-43a8-8d69-f426af23f551
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e7dd639cbf1ef076dee6e447f317533bf12dae10
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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