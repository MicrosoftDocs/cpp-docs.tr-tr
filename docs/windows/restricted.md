---
title: "kısıtlı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.restricted
dev_langs: C++
helpviewer_keywords: restricted attribute
ms.assetid: 504a96be-b904-4269-8be1-920feba201b4
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c6a6b0172b0078dee659964b36ec37464ec1705d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="restricted"></a>kısıtlı
Bir modül, arabirim veya görüntüleme arabirimi üyesi rasgele çağrılamaz belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ restricted(  
   interfaces  
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `interfaces`  
 Rasgele bir COM nesnesi üzerinde çağrılamaz bir veya daha fazla arabirim. Bu parametre yalnızca bir sınıfa uygulandığında geçerli olur.  
  
## <a name="remarks"></a>Açıklamalar  
 **Kısıtlı** C++ özniteliğine sahip ile aynı işlevselliği [kısıtlı](http://msdn.microsoft.com/library/windows/desktop/aa367157) MIDL özniteliği.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kodu nasıl kullanılacağını gösterir **kısıtlı** özniteliği:  
  
```  
// cpp_attr_ref_restricted.cpp  
// compile with: /LD  
#include "windows.h"  
#include "unknwn.h"  
[module(name="MyLib")];  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface a  
{  
};  
  
[object, uuid("00000000-0000-0000-0000-000000000002")]  
__interface b  
{  
};  
  
[coclass, restricted(a,b), uuid("00000000-0000-0000-0000-000000000003")]  
class c : public a, public b  
{  
};  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|Yöntemi, arabirim `interface`, **sınıfı**,`struct`|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|**coclass'ı** (uygulandığında **sınıfı** veya `struct`)|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Arabirim öznitelikleri](../windows/interface-attributes.md)   
 [Yöntem öznitelikleri](../windows/method-attributes.md)   
