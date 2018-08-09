---
title: dize (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.string
dev_langs:
- C++
helpviewer_keywords:
- string attribute
ms.assetid: ddde900a-2e99-4fcd-86e8-57e1bdba7c93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 459f786863f7d10797008b87e276afb0c95e184a
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40020092"
---
# <a name="string-c"></a>string (C++)
Bildiren tek boyutlu **char**, **wchar_t**, `byte` (veya eşdeğer) dizi ya da böyle bir dizinin işaretçisi gerekir kabul bir dize.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
[string]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **Dize** C++ özniteliği ile aynı işlevlere sahip [dize](http://msdn.microsoft.com/library/windows/desktop/aa367270) MIDL özniteliği.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod nasıl kullanılacağını gösterir **dize** bir arabirimde ve bir tür tanımı:  
  
```cpp  
// cpp_attr_ref_string.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="ATLFIRELib")];  
[export, string] typedef char a[21];  
[dispinterface, restricted, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IFireTabCtrl  
{  
   [id(1)] HRESULT Method3([in, string] char *pC);  
};  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**İçin geçerlidir**|Dizi veya işaretçiyi bir dizi, arabirimi parametreyi, arabirim yöntemi|  
|**Tekrarlanabilir**|Hayır|  
|**Gerekli öznitelikleri**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Dizi öznitelikleri](../windows/array-attributes.md)   
 [export](../windows/export.md)   