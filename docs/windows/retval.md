---
title: retval | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.retval
dev_langs:
- C++
helpviewer_keywords:
- retval attribute
ms.assetid: bfa16f08-157d-4eea-afde-1232c54b8501
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1c0bf7ecd989b51a17c853c6d2986db204c3ce34
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33888727"
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
