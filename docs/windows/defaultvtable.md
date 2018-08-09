---
title: defaultvtable | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.defaultvtable
dev_langs:
- C++
helpviewer_keywords:
- defaultvtable attribute
ms.assetid: 5b3ed483-f69e-44dd-80fc-952028eb9d73
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 34850646e40ffa9cbd3185b13fdaa93d7c873787
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39651446"
---
# <a name="defaultvtable"></a>defaultvtable
Varsayılan vtable arabirim bir COM nesnesi için bir arabirim tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
[ defaultvtable(  
   interface  
) ]  
```  
  
### <a name="parameters"></a>Parametreler  
 *interface*  
 COM nesnesi için varsayılan vtable olmasını istediğiniz belirtilen arabirim.  
  
## <a name="remarks"></a>Açıklamalar  
 **Defaultvtable** C++ özniteliği ile aynı işlevlere sahip [defaultvtable](http://msdn.microsoft.com/library/windows/desktop/aa366795) MIDL özniteliği.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod öznitelikleri kullanan bir sınıf üzerinde gösterir. **defaultvtable** bir varsayılan arabirim belirtmek için:  
  
```cpp  
// cpp_attr_ref_defaultvtable.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLib")];  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMyI1 {  
   HRESULT x();  
};  
  
[object, uuid("00000000-0000-0000-0000-000000000002")]  
__interface IMyI2 {  
   HRESULT x();  
};  
  
[object, uuid("00000000-0000-0000-0000-000000000003")]  
__interface IMyI3 {  
   HRESULT x();  
};  
  
[coclass, source(IMyI3, IMyI1), default(IMyI3, IMyI2), defaultvtable(IMyI1),  
uuid("00000000-0000-0000-0000-000000000004")]  
class CMyC3 : public IMyI3 {};  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**İçin geçerlidir**|**sınıf**, **yapısı**|  
|**Tekrarlanabilir**|Hayır|  
|**Gerekli öznitelikleri**|**coclass**|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Daha fazla bilgi için [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Sınıf Öznitelikleri](../windows/class-attributes.md)   