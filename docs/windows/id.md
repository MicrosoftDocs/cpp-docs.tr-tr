---
title: Kimliği | Microsoft Docs
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
ms.openlocfilehash: 6c674765a0dfc06648d64a2b3b4e820bb467e700
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="id"></a>kimlik
Belirten bir `dispid` parametresi için bir üye işlevi (bir özellik veya bir arabirim veya görüntüleme arabirimi bir yöntemi).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ id(  
   dispid  
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dispid`  
 Arabirim yöntemini gönderme kimliği.  
  
## <a name="remarks"></a>Açıklamalar  
 **Kimliği** C++ özniteliğine sahip ile aynı işlevselliği [kimliği](http://msdn.microsoft.com/library/windows/desktop/aa367040) MIDL özniteliği.  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [bağlanabilirse](../windows/bindable.md) nasıl kullanılacağına ilişkin bir örnek **kimliği**.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|Arabirim yöntemi|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Yöntem öznitelikleri](../windows/method-attributes.md)   
 [Veri üyesi öznitelikleri](../windows/data-member-attributes.md)   
 [DefaultValue](../windows/defaultvalue.md)   
 [İçinde](../windows/in-cpp.md)   
 [out](../windows/out-cpp.md)   
