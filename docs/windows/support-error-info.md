---
title: support_error_info | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.support_error_info
dev_langs:
- C++
helpviewer_keywords:
- support_error_info attribute
ms.assetid: 20a2b55c-4738-4b35-a71d-e5e9c3a7e3bc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b8fec0ff1f76485700199847615ac2d8fcf9e5eb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="supporterrorinfo"></a>support_error_info
Implements ayrıntılı hataları döndürmek için destek.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ support_error_info(  
   error_interface=uuid  
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 **error_interface**  
 Arabirimi uygulama tanımlayıcısını **IErrorInfo**.  
  
## <a name="remarks"></a>Açıklamalar  
 **Support_error_info** C++ öznitelik istemciye hedef nesnesi tarafından karşılaşılan ayrıntılı, bağlamsal hatası döndürmek için destek uygular. Hataları, yöntemlerini desteklemek nesne için **IErrorInfo** nesne tarafından arabirimi uygulanmadı. Daha fazla bilgi için bkz: [destekleyen IDispatch ve IErrorInfo](../atl/supporting-idispatch-and-ierrorinfo.md).  
  
 Bu öznitelik ekler [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) hedef nesnesi için temel sınıf olarak sınıfı. Bu varsayılan uygulamasında sonuçları **ISupportErrorInfo** ve tek bir arabirim bir nesne üzerinde hataları oluşturduğunda kullanılabilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod, varsayılan desteği ekler **ISupportErrorInfo** arabirimini `CMyClass` nesnesi.  
  
```  
// cpp_attr_ref_support_error_info.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name="mymod")];  
[object, uuid("f0b17d66-dc6e-4662-baaf-76758e09c878")]  
__interface IMyErrors  
{  
};  
  
[ coclass, support_error_info("IMyErrors"),  
  uuid("854dd392-bdc7-4781-8667-8757936f2a4f") ]  
class CMyClass  
{  
};  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|**class**|  
|**Yinelenebilir**|Evet|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COM öznitelikleri](../windows/com-attributes.md)   
 [Sınıf Öznitelikleri](../windows/class-attributes.md)   
