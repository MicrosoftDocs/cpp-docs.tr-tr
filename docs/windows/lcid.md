---
title: LCID | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.lcid
dev_langs:
- C++
helpviewer_keywords:
- LCID attribute
ms.assetid: 7f248c69-ee1c-42c3-9411-39cf27c9f43d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 919bf90fad228a3d7b4f574072e5f315da6427d8
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39602706"
---
# <a name="lcid"></a>lcid
Bir işlev için bir yerel ayar tanımlayıcısı geçirmenize olanak tanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[lcid]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **LCID** C++ özniteliği işlevselliğini uygulayan [LCID](http://msdn.microsoft.com/library/windows/desktop/aa367067) MIDL özniteliği. Yerel bir kitaplığı bloğu için uygulamak istediğiniz kullanırsanız **LCID =** `lcid` parametresi [Modülü](../windows/module-cpp.md) özniteliği.  
  
## <a name="example"></a>Örnek  
  
```cpp  
// cpp_attr_ref_lcid.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLibrary")];  
typedef long HRESULT;  
  
[dual, uuid("2F5F63F1-16DA-11d2-9E7B-00C04FB926DA")]  
__interface IStatic {  
   HRESULT MyFunc([in, lcid] long LocaleID, [out, retval] BSTR * ReturnVal);  
};  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**İçin geçerlidir**|Parametre arabirimi|  
|**Tekrarlanabilir**|Hayır|  
|**Gerekli öznitelikleri**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Daha fazla bilgi için [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Parametre Öznitelikleri](../windows/parameter-attributes.md)   