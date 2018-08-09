---
title: salt okunur (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.readonly
dev_langs:
- C++
helpviewer_keywords:
- readonly attribute
ms.assetid: 1246cadd-5304-43a9-beea-51153d12704d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 05a46e099643602867aaa807e915e419054a8d60
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40016011"
---
# <a name="readonly-c"></a>readonly (C++)
Bir veri üyesine atama yasaklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
[readonly]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **Salt okunur** C++ özniteliği ile aynı işlevlere sahip [salt okunur](http://msdn.microsoft.com/library/windows/desktop/aa367152) MIDL özniteliği.  
  
 Bir yöntem parametresi değiştirilmesini engellemek istiyorsanız, ardından kullanmak [içinde](../windows/in-cpp.md) özniteliği.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod, bir kullanımını göstermektedir. **salt okunur** özniteliği:  
  
```cpp  
// cpp_attr_ref_readonly.cpp  
// compile with: /LD  
[idl_quote("midl_pragma warning(disable:2461)")];  
#include "unknwn.h"  
[module(name="ATLFIRELib")];  
  
[dispinterface, uuid(11111111-1111-1111-1111-111111111111)]  
__interface IFireTabCtrl  
{  
   [readonly, id(1)] int i();  
};  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**İçin geçerlidir**|Arabirim yöntemi|  
|**Tekrarlanabilir**|Hayır|  
|**Gerekli öznitelikleri**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Veri Üyesi Öznitelikleri](../windows/data-member-attributes.md)   