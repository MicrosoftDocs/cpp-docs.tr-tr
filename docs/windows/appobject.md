---
title: appobject | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.appobject
dev_langs: C++
helpviewer_keywords: appobject attribute
ms.assetid: 8ce30b73-e945-403e-a755-6bc78078a695
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 19462987cf4f9b5cc295766a694f01b8b4fac8ba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="appobject"></a>appobject
Bir tam .exe uygulamayla ilişkili olan ve coclass'ı özelliklerini ve işlevlerini bu genel olarak kullanılabilir olduğunu gösterir bir uygulama nesnesi olarak coclass'ı tanımlayan [tür kitaplığı](../mfc/automation-clients-using-type-libraries.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
[appobject]  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **Appobject** C++ özniteliğine sahip ile aynı işlevselliği [appobject](http://msdn.microsoft.com/library/windows/desktop/aa366726) MIDL özniteliği.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kodu içeren bir öznitelik blok öncesinde bir basit sınıf tanımını gösterir **appobject**:  
  
```  
// cpp_attr_ref_appobject.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLib", uuid="f1ce17f0-a5df-4d26-95f6-0a122197ac5b")];  
  
[object, uuid="905de6db-7a12-45ab-9f8b-b39f5112f010"]  
__interface ICustom {};  
  
[coclass, appobject,uuid="00395340-745f-4b69-bd58-e2921452b9fc"]  
class A : public ICustom {  
   int i;  
};  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|**sınıf**,`struct`|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|**coclass**|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Sınıf öznitelikleri](../windows/class-attributes.md)   
 [Typedef, Enum, Union ve Struct Öznitelikleri](../windows/typedef-enum-union-and-struct-attributes.md)   
