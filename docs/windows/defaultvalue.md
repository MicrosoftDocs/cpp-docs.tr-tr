---
title: DefaultValue | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.defaultvalue
dev_langs:
- C++
helpviewer_keywords:
- defaultvalue attribute
ms.assetid: efa5d050-b2cc-4d9e-9b8e-79954f218d3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: deda09913f2774a2b3b246a285df0c8b6f1c62eb
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652831"
---
# <a name="defaultvalue"></a>defaultvalue
Belirtilmiş bir isteğe bağlı parametre için bir varsayılan değer belirtimi sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
[ defaultvalue= value ]  
```  
  
### <a name="parameters"></a>Parametreler  
 *value*  
 Parametre için varsayılan değer.  
  
## <a name="remarks"></a>Açıklamalar  
 **Defaultvalue** C++ özniteliği ile aynı işlevlere sahip [defaultvalue](http://msdn.microsoft.com/library/windows/desktop/aa366793) MIDL özniteliği.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod, bir arabirim yöntemini kullanarak göstermektedir **defaultvalue** özniteliği:  
  
```cpp  
// cpp_attr_ref_defaultvalue.cpp  
// compile with: /LD  
#include <windows.h>  
  
[export] typedef long HRESULT;  
[export, ptr, string] typedef unsigned char * MY_STRING_TYPE;  
  
[  uuid("479B29EE-9A2C-11D0-B696-00A0C903487A"),  
   dual, oleautomation,  
   helpstring("IFireTabCtrl Interface"),  
   helpcontext(122), pointer_default(unique) ]  
  
__interface IFireTabCtrl : IDispatch {  
   [bindable, propget] HRESULT get_Size([out, retval, defaultvalue("33")] long *nSize);  
   [bindable, propput] HRESULT put_Size([in] int nSize);  
};  
  
[ module(name="ATLFIRELib", uuid="479B29E1-9A2C-11D0-B696-00A0C903487A",  
      version="1.0", helpstring="ATLFire 1.0 Type Library") ];  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**İçin geçerlidir**|Parametre arabirimi|  
|**Tekrarlanabilir**|Hayır|  
|**Gerekli öznitelikleri**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Daha fazla bilgi için [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Parametre öznitelikleri](../windows/parameter-attributes.md)   
 [Çıkış](../windows/out-cpp.md)   
 [retval](../windows/retval.md)   
 [İçinde](../windows/in-cpp.md)   
 [pointer_default](../windows/pointer-default.md)   
 [benzersiz](../windows/unique-cpp.md)   