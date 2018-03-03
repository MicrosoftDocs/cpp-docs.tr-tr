---
title: retval | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.retval
dev_langs:
- C++
helpviewer_keywords:
- retval attribute
ms.assetid: bfa16f08-157d-4eea-afde-1232c54b8501
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cf7aa0cf8dd9767f603807ee18e23fe02d3446c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="retval"></a>retval
Üye dönüş değerini parametre belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
[retval]  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **Retval** C++ özniteliğine sahip ile aynı işlevselliği [retval](http://msdn.microsoft.com/library/windows/desktop/aa367158) MIDL özniteliği.  
  
 **retval** son bağımsız değişken bir işlevin bildiriminde görünmesi gerekir.  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [bağlanabilirse](../windows/bindable.md) bir örnek kullanım için **retval**.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|Arabirim parametresi, arabirim yöntemi|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|**out**|  
|**Geçersiz öznitelikler**|**in**|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Parametre öznitelikleri](../windows/parameter-attributes.md)   
 [Yöntem Öznitelikleri](../windows/method-attributes.md)   
