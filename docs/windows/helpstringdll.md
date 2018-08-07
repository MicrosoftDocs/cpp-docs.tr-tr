---
title: helpstringdll | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.helpstringdll
dev_langs:
- C++
helpviewer_keywords:
- helpstringdll attribute [C++]
ms.assetid: 121271fa-f061-492b-b87f-bbfcf4b02e7b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 27303f294f2414e2ea3f15de0c5bbfb1723628aa
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570086"
---
# <a name="helpstringdll"></a>helpstringdll
Belge dize arama (yerelleştirme) gerçekleştirmek için kullanılacak DLL'in adını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[ helpstringdll(  
   "string"  
) ]  
```  
  
### <a name="parameters"></a>Parametreler  
 *string*  
 Belge dize arama gerçekleştirmek için kullanılacak DLL.  
  
## <a name="remarks"></a>Açıklamalar  
 **Helpstringdll** C++ özniteliği ile aynı işlevlere sahip [helpstringdll](http://msdn.microsoft.com/library/windows/desktop/aa366860) MIDL özniteliği.  
  
## <a name="example"></a>Örnek  
  
```cpp  
// cpp_attr_ref_helpstringdll.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLib", helpstringdll="xx.dll")];  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMyI   
{  
   HRESULT xxx();  
};  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**İçin geçerlidir**|**sınıf**, **arabirimi**, arabirim yöntemi|  
|**Tekrarlanabilir**|Hayır|  
|**Gerekli öznitelikleri**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Daha fazla bilgi için [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Arabirim öznitelikleri](../windows/interface-attributes.md)   
 [Sınıf öznitelikleri](../windows/class-attributes.md)   
 [Yöntem Öznitelikleri](../windows/method-attributes.md)   