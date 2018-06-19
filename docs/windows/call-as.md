---
title: call_as | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.call_as
dev_langs:
- C++
helpviewer_keywords:
- call_as attribute
ms.assetid: a09d7f1f-353b-4870-9b45-f0284161695d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 68707ea7e00665d12165c7838b1a2ad3440f944d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33860872"
---
# <a name="callas"></a>call_as
Sağlayan bir [yerel](../windows/local-cpp.md) uzak işlev çağrıldığında, yerel işlevi çağrılır böylece uzak işlev için eşleştirilecek işlevi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ call_as(  
   function  
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 *İşlevi*  
 Uzak işlev çağrıldığında çağrılacak istediğiniz yerel işlev.  
  
## <a name="remarks"></a>Açıklamalar  
 **Call_as** C++ özniteliğine sahip ile aynı işlevselliği [call_as](http://msdn.microsoft.com/library/windows/desktop/aa366748) MIDL özniteliği.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod nasıl kullanabileceğinizi gösterir **call_as** nonremotable işlevi eşlemek için (**f1**) Uzaktan erişilebilir işlevi (**Remf1**):  
  
```  
// cpp_attr_ref_call_as.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="MyLib")];  
[dual, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMInterface {  
   [local] HRESULT f1 ( int i );  
   [call_as(f1)] HRESULT Remf1 ( int i );   
};  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|Arabirim yöntemi|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Yöntem öznitelikleri](../windows/method-attributes.md)   
 [Yerel](../windows/local-cpp.md)   
