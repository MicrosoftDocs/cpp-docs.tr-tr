---
title: pointer_default | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.pointer_default
dev_langs:
- C++
helpviewer_keywords:
- pointer_default attribute
ms.assetid: 2d0c7bbc-a1e8-4337-9e54-e304523e2735
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 98e3b9e78f46b14dfeca18a8e69538111d3ba219
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40010321"
---
# <a name="pointerdefault"></a>pointer_default
Parametre listelerindeki görünen üst düzey işaretçileri dışındaki tüm işaretçiler için varsayılan işaretçi özniteliğini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
[ pointer_default(  
   value  
) ]  
```  
  
### <a name="parameters"></a>Parametreler  
 *value*  
 İşaretçi türü tanımlayan bir değer: **ptr**, **ref**, veya **benzersiz**.  
  
## <a name="remarks"></a>Açıklamalar  
 **Pointer_default** C++ özniteliği ile aynı işlevlere sahip [pointer_default](http://msdn.microsoft.com/library/windows/desktop/aa367141) MIDL özniteliği.  
  
## <a name="example"></a>Örnek  
 Örneğin bakın [defaultvalue](../windows/defaultvalue.md) örnek kullanımı için **pointer_default**.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**İçin geçerlidir**|**interface**|  
|**Tekrarlanabilir**|Hayır|  
|**Gerekli öznitelikleri**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Arabirim Öznitelikleri](../windows/interface-attributes.md)   