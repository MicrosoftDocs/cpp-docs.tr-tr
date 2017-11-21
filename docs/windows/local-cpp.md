---
title: Yerel (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.local
dev_langs: C++
helpviewer_keywords: local attribute
ms.assetid: 35cdd668-bd8e-492a-b7b8-263e7b662437
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 007d95d5db0785deae08744b46738d7188e4da70
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
|**Geçersiz öznitelikler**|**görüntüleme arabirimi**|  
  
 Daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Arabirim öznitelikleri](../windows/interface-attributes.md)   
 [Yöntem öznitelikleri](../windows/method-attributes.md)   
 [call_as](../windows/call-as.md)   
