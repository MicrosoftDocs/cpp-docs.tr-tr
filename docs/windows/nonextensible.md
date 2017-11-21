---
title: nonextensible | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.nonextensible
dev_langs: C++
helpviewer_keywords: nonextensible attribute
ms.assetid: c7ef1554-809f-4ea0-a7cd-dc7786d40c3e
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 277e8ad4b19f5da5cf0d5574e240915ddc9b525c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="nonextensible"></a>nonextensible
Belirleyen `IDispatch` uygulaması yalnızca özellikleri içerir ve yöntemleri arabirimi açıklamasında listelenen ve çalışma zamanında ek üyeleriyle genişletilemez.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
[nonextensible]  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **Nonextensible** C++ özniteliğine sahip ile aynı işlevselliği [nonextensible](http://msdn.microsoft.com/library/windows/desktop/aa367120) MIDL özniteliği.  
  
 Kullanımı **nonextensible** de gerektirir [oleautomation](../windows/oleautomation.md) özniteliği.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod bir kullanımını gösterir **nonextensible** özniteliği:  
  
```  
// cpp_attr_ref_nonextensible.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="ATLFIRELib")];  
[export] typedef long HRESULT;  
  
[dual, nonextensible, ms_union, oleautomation,   
uuid("00000000-0000-0000-0000-000000000001")]  
__interface IFireTabCtrl  
{  
   HRESULT procedure (int i);   
};  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|`interface`|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|**çift** ve **oleautomation**, veya **görüntüleme arabirimi**|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Arabirim öznitelikleri](../windows/interface-attributes.md)   
