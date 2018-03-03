---
title: LCID | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.lcid
dev_langs:
- C++
helpviewer_keywords:
- LCID attribute
ms.assetid: 7f248c69-ee1c-42c3-9411-39cf27c9f43d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 36ccb085c2f6128012d446f6be15dff94c718e35
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="lcid"></a>lcid
Yerel ayar tanımlayıcısı bir işleve geçirmenize olanak sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
[lcid]  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **LCID** C++ öznitelik uygulayan işlevselliğini [LCID](http://msdn.microsoft.com/library/windows/desktop/aa367067) MIDL özniteliği. Kitaplık bloğu için yerel ayar uygulamak isterseniz kullanırsanız **LCID =** `lcid` parametresi [Modülü](../windows/module-cpp.md) özniteliği.  
  
## <a name="example"></a>Örnek  
  
```  
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
|**Uygulandığı öğe:**|Parametre arabirimi|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Parametre Öznitelikleri](../windows/parameter-attributes.md)   
