---
title: satype | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.satype
dev_langs: C++
helpviewer_keywords: satype attribute
ms.assetid: 1716590b-6bcb-4aba-b1bc-82f7335f02c3
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 40aa6aa0b8270cf910fe7449af32ae877544a40e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="satype"></a>satype
Veri türünü belirtir **SAFEARRAY** yapısı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ satype(  
   data_type  
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 *data_type*  
 Veri türü için **SAFEARRAY** parametre olarak bir arabirim yönteme geçirilen veri yapısı.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|Arabirim parametresi, arabirim yöntemi|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
## <a name="remarks"></a>Açıklamalar  
 **Satype** C++ özniteliği belirtir. veri türünü **SAFEARRAY**.  
  
> [!NOTE]
>  Yöneltme düzeyini gelen bırakılan **SAFEARRAY** nasıl .cpp dosyasında bildirilen oluşturulan .idl dosyadan işaretçi.  
  
## <a name="example"></a>Örnek  
  
```  
// cpp_attr_ref_satype.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="MyModule")];  
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]  
__interface A {  
   [id(1)] HRESULT MyMethod ([in, satype("BSTR")] SAFEARRAY **p);  
};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici öznitelikleri](../windows/compiler-attributes.md)   
 [Parametre öznitelikleri](../windows/parameter-attributes.md)   
 [Yöntem öznitelikleri](../windows/method-attributes.md)   
 [Kimliği](../windows/id.md)   
