---
title: "Eşitleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.synchronize
dev_langs:
- C++
helpviewer_keywords:
- synchronize attribute
ms.assetid: 15fc8544-955d-4765-b3d5-0f619c8b3f40
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6d326a4069334a223db7824e5fa3bcaefbc97697
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="synchronize"></a>eşitle
Hedef yöntemin erişimi eşitler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
[synchronize]  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **Eşitleme** C++ öznitelik hedef yöntemin bir nesnenin eşitlemek için destek uygular. Eşitleme hedef yöntemin erişimini denetleyerek ortak bir kaynak (örneğin, bir sınıfın bir yöntem) kullanmak birden fazla nesne sağlar.  
  
 Bu öznitelik tarafından eklenen kod uygun çağırır `Lock` hedef yöntemin başındaki yöntemi (iş parçacığı modeli tarafından belirlenir). Yönteminden çıkıldı zaman `Unlock` otomatik olarak çağrılır. Bu işlevler hakkında daha fazla bilgi için bkz: [CComAutoThreadModule::Lock](../atl/reference/ccomautothreadmodule-class.md#lock)  
  
 Bu öznitelik gerektiren [coclass](../windows/coclass.md), [ProgID](../windows/progid.md), veya [vi_progid](../windows/vi-progid.md) özniteliği (veya bunlardan birini gelir başka bir öznitelik) de uygulanması aynı öğeye. Herhangi bir tek öznitelik kullanılırsa, diğer iki otomatik olarak uygulanır. Örneğin, varsa **ProgID** uygulanan **vi_progid** ve **coclass** da uygulanır.  
  
## <a name="example"></a>Örnek  
 Eşitleme için aşağıdaki kodu sağlar `UpdateBalance` yöntemi `CMyClass` nesnesi.  
  
```  
// cpp_attr_ref_synchronize.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module(name="SYNC")];  
  
[coclass,  
 threading(both),  
 vi_progid("MyProject.MyClass"),  
 progid("MyProject.MyClass.1"),  
 uuid("7a7baa0d-59b8-4576-b754-79d07e1d1cc3")  
]  
class CMyClass {  
   float m_nBalance;  
  
   [synchronize]  
   void UpdateBalance(float nAdjust) {  
      m_nBalance += nAdjust;  
   }  
};  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|Sınıf yöntemi, yöntemi|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Bir veya daha fazlasını: **coclass**, **ProgID**, veya **vi_progid**.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COM Öznitelikleri](../windows/com-attributes.md)   
