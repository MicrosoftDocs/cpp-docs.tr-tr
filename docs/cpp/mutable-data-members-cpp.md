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
ms.openlocfilehash: adc8f9c456d28089d57bc1f13b61ad8efa10b6b6
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402926"
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
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)