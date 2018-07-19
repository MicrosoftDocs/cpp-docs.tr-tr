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
ms.openlocfilehash: 65d2fc42021a01a1260b57f9516e53c439c8e604
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37948214"
---
# <a name="mutable-data-members-c"></a>Değişebilir Veri Üyeleri (C++)
Bu anahtar sözcüğü, yalnızca bir sınıfın statik olmayan ve sabit olmayan veri üyelerine uygulanabilir. Bir veri üyesi bildirilirse **değişebilir**, sonra da bu veri üyesi için bir değer atamak için yasal bir **const** üye işlevi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
mutable member-variable-declaration;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Örneğin, aşağıdaki kod hatasız çünkü derleyeceği `m_accessCount` olarak bildirilmiş **değişebilir**ve bu nedenle tarafından değiştirilebilir `GetFlag` olsa bile `GetFlag` const üye işlevi olmasıdır.  
  
```cpp 
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