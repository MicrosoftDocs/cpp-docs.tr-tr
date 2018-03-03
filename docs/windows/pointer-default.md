---
title: pointer_default | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.pointer_default
dev_langs:
- C++
helpviewer_keywords:
- pointer_default attribute
ms.assetid: 2d0c7bbc-a1e8-4337-9e54-e304523e2735
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b55bf95c7abdffe8dd0a0e0071d86f06baad344e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="pointerdefault"></a>pointer_default
Parametre listelerinde görüntülenen en üst düzey işaretçileri dışındaki tüm işaretçiler varsayılan işaretçi özniteliğini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ pointer_default(  
   value  
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 *value*  
 İşaretçi türünün tanımlayan bir değer: **ptr**, `ref`, veya **benzersiz**.  
  
## <a name="remarks"></a>Açıklamalar  
 **Pointer_default** C++ özniteliğine sahip ile aynı işlevselliği [pointer_default](http://msdn.microsoft.com/library/windows/desktop/aa367141) MIDL özniteliği.  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [defaultvalue](../windows/defaultvalue.md) bir örnek kullanım için **pointer_default**.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|`interface`|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Arabirim Öznitelikleri](../windows/interface-attributes.md)   
