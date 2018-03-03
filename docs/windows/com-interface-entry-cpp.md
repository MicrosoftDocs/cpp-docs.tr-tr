---
title: com_interface_entry (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.com_interface_entry
dev_langs:
- C++
helpviewer_keywords:
- com_interface_entry attribute
ms.assetid: 10368f81-b99b-4a0f-ba4f-a142e6911a5c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 58c74602c4170cbe0816dcdf14e0196cca44af42
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cominterfaceentry-c"></a>com_interface_entry (C++)
COM eşlemesi hedef sınıfın içine bir arabirim girdisi ekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
     [ com_interface_entry(   
  com_interface_entry  
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 *com_interface_entry*  
 Giriş gerçek metnini içeren bir dize. Olası değerler listesi için bkz: [COM_INTERFACE_ENTRY makroları](../atl/reference/com-interface-entry-macros.md).  
  
## <a name="remarks"></a>Açıklamalar  
 `com_interface_entry` C++ öznitelik hedef nesne COM arabirimi eşlemeye bir karakter dizesi unabridged içeriğini ekler. Öznitelik bir kez hedef nesneye uyguladıysanız, giriş varolan arabirim eşlemesi başına içine eklenir. Öznitelik sürekli olarak aynı hedef nesnesi uyguladıysanız, girişleri alındıkları sırayla arabirim eşlemesi başına eklenir.  
  
 Bu öznitelik gerektiren [coclass](../windows/coclass.md), [ProgID](../windows/progid.md), veya [vi_progid](../windows/vi-progid.md) özniteliği (veya bunlardan birini gelir başka bir öznitelik) de uygulanması aynı öğeye. Herhangi bir tek öznitelik kullanılırsa, diğer iki otomatik olarak uygulanır. Örneğin, varsa **ProgID** uygulanan **vi_progid** ve **coclass** da uygulanır.  
  
 Çünkü ilk kullanımını `com_interface_entry` arabirim eşlemesi başında eklenecek yeni arabirimi neden olan aşağıdaki COM_INTERFACE_ENTRY türlerden biri olmalıdır:  
  
-   COM_INTERFACE_ENTRY  
  
-   COM_INTERFACE_ENTRY_IID  
  
-   COM_INTERFACE_ENTRY2  
  
-   COM_INTERFACE_ENTRY2_IID  
  
 Ek kullanım `com_interface_entry` özniteliği, desteklenen tüm COM_INTERFACE_ENTRY türleri kullanabilirsiniz.  
  
 ATL ilk giriş arabirimi eşlemesinde kimliği olarak kullandığı için bu kısıtlama gereklidir **IUnknown**; bu nedenle, giriş geçerli bir arabirim olmalıdır. Örneğin, aşağıdaki kod örneği arabirim eşlemesi ilk giriş gerçek bir COM arabirimi belirtmediğinden geçersiz.  
  
```  
[ coclass, com_interface_entry =  
    "COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)"  
]  
   class CMyClass  
   {  
   };  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod, var olan COM arabirimi haritasını için iki giriş ekler **CMyBaseClass**. İlk standart bir arabirimdir ve ikinci gizler **IDebugTest** arabirimi.  
  
```  
// cpp_attr_ref_com_interface_entry.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name ="ldld")];  
  
[ object,  
  uuid("7dbebed3-d636-4917-af62-c767a720a5b9")]  
__interface IDebugTest{};  
  
[ object,  
  uuid("2875ceac-f94b-4087-8e13-d13dc167fcfc")]  
__interface IMyClass{};  
  
[ coclass,  
  com_interface_entry ("COM_INTERFACE_ENTRY (IMyClass)"),  
  com_interface_entry ("COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)"),  
  uuid("b85f8626-e76e-4775-b6a0-4826a9e94af2")  
]  
  
class CMyClass: public IMyClass, public IDebugTest  
{  
};  
```  
  
 Sonuçta elde edilen COM Nesne eşlemesi için **CMyBaseClass** aşağıdaki gibidir:  
  
```  
BEGIN_COM_MAP(CMyClass)  
    COM_INTERFACE_ENTRY (IMyClass)  
    COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)  
    COM_INTERFACE_ENTRY(IMyClass)  
    COM_INTERFACE_ENTRY2(IDispatch, IMyClass)  
    COM_INTERFACE_ENTRY(IDebugTest)  
    COM_INTERFACE_ENTRY(IProvideClassInfo)  
END_COM_MAP()  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|**sınıf**,`struct`|  
|**Yinelenebilir**|Evet|  
|**Gerekli öznitelikler**|Bir veya daha fazlasını: **coclass**, **ProgID**, veya **vi_progid**.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COM öznitelikleri](../windows/com-attributes.md)   
 [Sınıf öznitelikleri](../windows/class-attributes.md)   
 [Typedef, Enum, Union ve Struct Öznitelikleri](../windows/typedef-enum-union-and-struct-attributes.md)   
