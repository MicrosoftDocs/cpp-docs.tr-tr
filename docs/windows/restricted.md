---
title: kısıtlı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.restricted
dev_langs:
- C++
helpviewer_keywords:
- restricted attribute
ms.assetid: 504a96be-b904-4269-8be1-920feba201b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f79b4e53947e0e87fb70211ca40bc54f4500855f
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39602778"
---
# <a name="restricted"></a>kısıtlı
Bir modül, arabirim veya dispinterface üyesi rasgele çağrılamaz belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[ restricted(  
   interfaces  
) ]  
```  
  
### <a name="parameters"></a>Parametreler  
 *Arabirimleri*  
 Rasgele bir COM nesnesi üzerinde çağrılamaz bir veya daha fazla arabirim. Bu parametre, yalnızca bir sınıfa uygulandığında geçerlidir.  
  
## <a name="remarks"></a>Açıklamalar  
 **Kısıtlı** C++ özniteliği ile aynı işlevlere sahip [kısıtlı](http://msdn.microsoft.com/library/windows/desktop/aa367157) MIDL özniteliği.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod nasıl kullanılacağını gösterir **kısıtlı** özniteliği:  
  
```cpp  
// cpp_attr_ref_restricted.cpp  
// compile with: /LD  
#include "windows.h"  
#include "unknwn.h"  
[module(name="MyLib")];  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface a  
{  
};  
  
[object, uuid("00000000-0000-0000-0000-000000000002")]  
__interface b  
{  
};  
  
[coclass, restricted(a,b), uuid("00000000-0000-0000-0000-000000000003")]  
class c : public a, public b  
{  
};  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**İçin geçerlidir**|Arabirim yöntemini **arabirimi**, **sınıfı**, **yapısı**|  
|**Tekrarlanabilir**|Hayır|  
|**Gerekli öznitelikleri**|**coclass'ı** (uygulandığında **sınıfı** veya **yapı**)|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Arabirim öznitelikleri](../windows/interface-attributes.md)   
 [Yöntem Öznitelikleri](../windows/method-attributes.md)   