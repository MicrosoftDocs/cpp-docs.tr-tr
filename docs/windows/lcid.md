---
title: LCID | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.lcid
dev_langs: C++
helpviewer_keywords: LCID attribute
ms.assetid: 7f248c69-ee1c-42c3-9411-39cf27c9f43d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fc811d4522872f14d86ea08fc93e5253830f779b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Parametre öznitelikleri](../windows/parameter-attributes.md)   
