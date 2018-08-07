---
title: kimlik | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.id
dev_langs:
- C++
helpviewer_keywords:
- id attribute
ms.assetid: a48d2c99-c5d2-4f46-bf96-5ac88dcb5d0c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b36a45dad71f2144c3e3d0990ab7715d00e8ff21
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39605714"
---
# <a name="id"></a>kimlik
Belirtir bir *DISPID* (bir özellik veya bir arabirim veya dispinterface bir yöntem), bir üye işlev için parametre.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[ id(  
   dispid  
) ]  
```  
  
### <a name="parameters"></a>Parametreler  
 *DISPID*  
 Arabirim yöntemi için gönderme kimliği.  
  
## <a name="remarks"></a>Açıklamalar  
 **Kimliği** C++ özniteliği ile aynı işlevlere sahip [kimliği](http://msdn.microsoft.com/library/windows/desktop/aa367040) MIDL özniteliği.  
  
## <a name="example"></a>Örnek  
 Örneğin bakın [bağlanabilir](../windows/bindable.md) nasıl kullanılacağına ilişkin bir örnek **kimliği**.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**İçin geçerlidir**|Arabirim yöntemi|  
|**Tekrarlanabilir**|Hayır|  
|**Gerekli öznitelikleri**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Daha fazla bilgi için [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Yöntem öznitelikleri](../windows/method-attributes.md)   
 [Veri üyesi öznitelikleri](../windows/data-member-attributes.md)   
 [DefaultValue](../windows/defaultvalue.md)   
 [İçinde](../windows/in-cpp.md)   
 [out](../windows/out-cpp.md)   