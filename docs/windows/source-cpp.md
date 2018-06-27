---
title: Kaynak (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.source
dev_langs:
- C++
helpviewer_keywords:
- source attribute
ms.assetid: 1878d05d-7709-4e97-b114-c62f38f5140e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 11ee58fb2d500a7194fb08ee18b1af5cc7897830
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889868"
---
# <a name="source-c"></a>kaynak (C++)
Bir sınıf üzerinde bağlantı noktaları için COM nesnesinin kaynak arabirimleri belirtir. Özellik veya yöntem üye nesne veya olay kaynağı değişken döndürdüğünü gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ source(  
   interfaces  
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `interfaces`  
 Kaynak uyguladığınızda belirttiğiniz bir veya daha fazla arabirimleri bir sınıfa öznitelik. Kaynak bir özellik veya yöntem uygulandığında, bu parametre kullanılmaz.  
  
## <a name="remarks"></a>Açıklamalar  
 **Kaynak** C++ özniteliğine sahip ile aynı işlevselliği [kaynak](http://msdn.microsoft.com/library/windows/desktop/aa367166) MIDL özniteliği.  
  
 Kullanabileceğiniz [varsayılan](../windows/default-cpp.md) bir nesne için varsayılan kaynak arabirimi belirtmek için özniteliği.  
  
## <a name="example"></a>Örnek  
  
```  
// cpp_attr_ref_source.cpp  
// compile with: /LD  
#include "windows.h"  
#include "unknwn.h"  
[module(name="MyLib")];  
  
[object, uuid(11111111-1111-1111-1111-111111111111)]  
__interface b  
{  
   [id(0), propget, bindable, displaybind, defaultbind, requestedit]  
   HRESULT get_I([out, retval]long *i);  
};  
  
[object, uuid(11111111-1111-1111-1111-111111111131)]  
__interface c  
{  
   [id(0), propget, bindable, displaybind, defaultbind, requestedit]   
   HRESULT et_I([out, retval]long *i);  
};  
  
[coclass, default(c), uuid(11111111-1111-1111-1111-111111111132)]  
class N : public b  
{  
};  
  
[coclass, source(c), default(b, c), uuid(11111111-1111-1111-1111-111111111133)]  
class NN : public b  
{  
};  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|**sınıf**, `struct`, `interface`|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|**coclass'ı** (sınıfta veya yapı uygulandığında)|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Sınıf öznitelikleri](../windows/class-attributes.md)   
 [Yöntem öznitelikleri](../windows/method-attributes.md)   
 [coclass](../windows/coclass.md)   
