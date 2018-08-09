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
ms.openlocfilehash: a30598e617a4c68559d6932e20dadaf7f83dc2eb
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40015526"
---
# <a name="source-c"></a>kaynak (C++)
Sınıfta, COM nesnesinin kaynak arabirimleri için bağlantı noktalarını belirtir. Özellik veya yöntem üyesi bir nesne veya bir olay kaynağı olan Değişken döndürür gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
[ source(  
   interfaces  
) ]  
```  
  
### <a name="parameters"></a>Parametreler  
 *Arabirimleri*  
 Kaynak uyguladığınızda belirttiğiniz bir veya daha fazla arabirim bir sınıfa öznitelik. Kaynak bir özellik veya yöntem uygulandığında, bu parametre kullanılmaz.  
  
## <a name="remarks"></a>Açıklamalar  
 **Kaynak** C++ özniteliği ile aynı işlevlere sahip [kaynak](http://msdn.microsoft.com/library/windows/desktop/aa367166) MIDL özniteliği.  
  
 Kullanabileceğiniz [varsayılan](../windows/default-cpp.md) nesnenin varsayılan kaynak arabirimi belirtmek için özniteliği.  
  
## <a name="example"></a>Örnek  
  
```cpp  
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
|**İçin geçerlidir**|**sınıf**, **yapı**, **arabirimi**|  
|**Tekrarlanabilir**|Hayır|  
|**Gerekli öznitelikleri**|`coclass` (sınıf veya yapı için uygulandığında)|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Sınıf öznitelikleri](../windows/class-attributes.md)   
 [Yöntem öznitelikleri](../windows/method-attributes.md)   
 [coclass](../windows/coclass.md)   