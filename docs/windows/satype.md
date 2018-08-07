---
title: satype | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.satype
dev_langs:
- C++
helpviewer_keywords:
- satype attribute
ms.assetid: 1716590b-6bcb-4aba-b1bc-82f7335f02c3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8a5376e0e830654c15dc31522b07ed53af4492bf
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39603400"
---
# <a name="satype"></a>satype
Veri türü belirtir `SAFEARRAY` yapısı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[ satype(  
   data_type  
) ]  
```  
  
### <a name="parameters"></a>Parametreler  
 *data_type*  
 Veri türü için `SAFEARRAY` arabirim yöntemi için parametre olarak geçirilen veri yapısı.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**İçin geçerlidir**|Arabirimi parametresi, arabirim yöntemi|  
|**Tekrarlanabilir**|Hayır|  
|**Gerekli öznitelikleri**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
## <a name="remarks"></a>Açıklamalar  
 **Satype** C++ öznitelik veri türü belirtir `SAFEARRAY`.  
  
> [!NOTE]
>  Yöneltme düzeyi düşürülmüştür `SAFEARRAY` nasıl .cpp dosyasında bildirilen öğesinden oluşturulan .idl dosyasındaki bir işaretçi.  
  
## <a name="example"></a>Örnek  
  
```cpp  
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
 [id](../windows/id.md)   