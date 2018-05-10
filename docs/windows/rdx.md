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
ms.openlocfilehash: 7647ca56e3159564826efa9caf438456b9ae3568
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
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
  
#### <a name="parameters"></a>Parametreler  
 `key`  
 Açılan veya oluşturulacak anahtarın adı.  
  
 `valuename`(isteğe bağlı)  
 Ayarlanacak değer alanını belirtir. Bu ada sahip bir değer alan anahtarı zaten mevcut değilse eklenir.  
  
 *regtype*  
 Eklenen kayıt defteri anahtar türü. Şunlardan biri olabilir: **metin**, **dword**, **ikili**, veya `CString`.  
  
## <a name="remarks"></a>Açıklamalar  
 **Rdx** C++ öznitelik oluşturur veya mevcut bir kayıt defteri anahtarı bir COM bileşeni için değiştirir. Öznitelik BEGIN_RDX_MAP makrosu hedef üye uygulayan nesneye ekler. `RegistryDataExchange`, BEGIN_RDX_MAP makrosu sonucunda eklenen işlev, kayıt defteri ve veri üyeleri arasında veri aktarmak için kullanılabilir  
  
 Bu öznitelik ile birlikte kullanılan [coclass](../windows/coclass.md), [ProgID](../windows/progid.md), veya [vi_progid](../windows/vi-progid.md) öznitelikleri ya da bunlardan birini gelir diğer öznitelikleri.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|**sınıf** veya `struct` üyesi|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod CMyClass COM bileşeni açıklayan sistem MyValue adlı bir kayıt defteri anahtarı ekler.  
  
```  
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
