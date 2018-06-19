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
ms.openlocfilehash: 17a57ad56402b345aa64e4e4fd02bc57dd7f0321
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33877923"
---
# <a name="local-c"></a>yerel (C++)
Arabirim üstbilgisinde kullanıldığında MIDL derleyici üstbilgi Oluşturucu olarak kullanmanıza olanak sağlar. Tek bir işlev kullanıldığında, kendisi için hiçbir saplamalar oluşturulan yerel bir yordam belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
[local]  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `local` C++ özniteliğine sahip ile aynı işlevselliği [yerel](http://msdn.microsoft.com/library/windows/desktop/aa367071) MIDL özniteliği.  
  
## <a name="example"></a>Örnek  
 Bkz: [call_as](../windows/call-as.md) nasıl kullanılacağına ilişkin bir örnek `local`.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|`interface`, arabirim yöntemi|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|**dispinterface**|  
  
 Daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Arabirim öznitelikleri](../windows/interface-attributes.md)   
 [Yöntem öznitelikleri](../windows/method-attributes.md)   
 [call_as](../windows/call-as.md)   
