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
ms.openlocfilehash: d6f17f44e520018f82dc82abe88427a2410d68e7
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39606357"
---
# <a name="retval"></a>retval
Üyenin dönüş değerini alan parametreyi belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[retval]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **Retval** C++ özniteliği ile aynı işlevlere sahip [retval](http://msdn.microsoft.com/library/windows/desktop/aa367158) MIDL özniteliği.  
  
 **retval** son bağımsız değişken işlevin bildiriminde yer almalıdır.  
  
## <a name="example"></a>Örnek  
 Örneğin bakın [bağlanabilir](../windows/bindable.md) örnek kullanımı için **retval**.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**İçin geçerlidir**|Arabirimi parametresi, arabirim yöntemi|  
|**Tekrarlanabilir**|Hayır|  
|**Gerekli öznitelikleri**|**out**|  
|**Geçersiz öznitelikler**|**in**|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Parametre öznitelikleri](../windows/parameter-attributes.md)   
 [Yöntem Öznitelikleri](../windows/method-attributes.md)   