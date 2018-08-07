---
title: RDX | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.rdx
dev_langs:
- C++
helpviewer_keywords:
- rdx attribute
ms.assetid: ff8e4312-c1ad-4934-bdaa-86f54409651e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3908a8f06d25416999fbf2c95dd258fbc19d456d
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39603132"
---
# <a name="rdx"></a>rdx
Bir kayıt defteri anahtarı oluşturur veya mevcut bir kayıt defteri anahtarı değiştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[ rdx(   
   key,   
   valuename=NULL,   
   regtype   
) ]  
```  
  
### <a name="parameters"></a>Parametreler  
 *Anahtarı*  
 Açılan veya oluşturulacak anahtar adı.  
  
 *ValueName* (isteğe bağlı)  
 Ayarlanacak değer alanını belirtir. Bu ada sahip bir değer alanı anahtarı zaten mevcut değilse eklenir.  
  
 *regtype*  
 Eklenen kayıt defteri anahtarı türü. Aşağıdakilerden biri olabilir: `text`, `dword`, `binary`, veya `CString`.  
  
## <a name="remarks"></a>Açıklamalar  
 **Rdx** C++ öznitelik oluşturur veya mevcut bir kayıt defteri anahtarı bir COM bileşeni için değiştirir. Öznitelik BEGIN_RDX_MAP makrosu hedef üye uygulayan nesneye ekler. `RegistryDataExchange`, BEGIN_RDX_MAP makronun sonucu olarak, eklenen bir işlev, kayıt defteri ve veri üyeleri arasında veri aktarmak için kullanılabilir  
  
 Bu öznitelik ile birlikte kullanılabilir [coclass'ı](../windows/coclass.md), [ProgID](../windows/progid.md), veya [vi_progid](../windows/vi-progid.md) öznitelikleri veya bunlardan birini gelir diğer öznitelikleri.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**İçin geçerlidir**|**sınıf** veya **yapı** üyesi|  
|**Tekrarlanabilir**|Hayır|  
|**Gerekli öznitelikleri**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod, MyValue CMyClass COM bileşeni açıklayan sisteme adlı bir kayıt defteri anahtarı ekler.  
  
```cpp  
// cpp_attr_ref_rdx.cpp  
// compile with: /LD /link /OPT:NOREF  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
  
[module (name="MyLib")];  
  
class CMyClass {  
public:  
   CMyClass() {  
      strcpy_s(m_sz, "SomeValue");  
   }  
  
   [ rdx(key = "HKCR\\MyApp.MyApp.1", valuename = "MyValue", regtype = "text")]   
   char m_sz[256];  
};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COM öznitelikleri](../windows/com-attributes.md)   
 [registration_script](../windows/registration-script.md)   