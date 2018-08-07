---
title: Yerel (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.local
dev_langs:
- C++
helpviewer_keywords:
- local attribute
ms.assetid: 35cdd668-bd8e-492a-b7b8-263e7b662437
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: efa937c1eaabb23fe5a360444f8c2105b735b260
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39604206"
---
# <a name="local-c"></a>yerel (C++)
Arabirimi başlığı kullanıldığında, MIDL derleyici üstbilgi Oluşturucu olarak kullanmanıza olanak tanır. Tek bir işlevde kullanıldığında, hiçbir saptamalar oluşturulan yerel bir yordam belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[local]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **Yerel** C++ özniteliği ile aynı işlevlere sahip [yerel](http://msdn.microsoft.com/library/windows/desktop/aa367071) MIDL özniteliği.  
  
## <a name="example"></a>Örnek  
 Bkz: [call_as](../windows/call-as.md) nasıl kullanılacağına ilişkin bir örnek **yerel**.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**İçin geçerlidir**|**arabirimi**, arabirim yöntemi|  
|**Tekrarlanabilir**|Hayır|  
|**Gerekli öznitelikleri**|Yok.|  
|**Geçersiz öznitelikler**|`dispinterface`|  
  
 Daha fazla bilgi için [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Arabirim öznitelikleri](../windows/interface-attributes.md)   
 [Yöntem öznitelikleri](../windows/method-attributes.md)   
 [call_as](../windows/call-as.md)   