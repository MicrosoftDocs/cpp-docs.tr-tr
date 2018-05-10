---
title: (C++) dahil | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.include
dev_langs:
- C++
helpviewer_keywords:
- include attribute
ms.assetid: d23f8b91-fe5b-48fa-9371-8bd73af7b8e3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a2c88dd610c1a0b8a8fee4e23da1b5ad844e989c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="include-c"></a>include (C++)
Oluşturulan .idl dosyasında dahil edilecek bir veya daha fazla üst bilgi dosyaları belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ include(  
   header_file  
) ];  
```  
  
#### <a name="parameters"></a>Parametreler  
 *header_file*  
 Oluşturulan .idl dosyasına dahil istediğiniz bir dosya adı.  
  
## <a name="remarks"></a>Açıklamalar  
 **Dahil** C++ öznitelik neden olan bir `#include` altına yerleştirilecek deyimi `import "docobj.idl"` oluşturulan .idl dosyasındaki deyimi.  
  
 **Dahil** C++ özniteliğine sahip ile aynı işlevselliği [dahil](http://msdn.microsoft.com/library/windows/desktop/aa367052) MIDL özniteliği.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği nasıl kullanılacağını gösterir **dahil**. Bu örnekte, yalnızca dosya include.h içeren bir # deyimi include.  
  
```  
// cpp_attr_ref_include.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[include(cpp_attr_ref_include.h)];  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|Her yerden|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Tek başına öznitelikler](../windows/stand-alone-attributes.md)   
 [İçeri aktarma](../windows/import.md)   
 [importidl](../windows/importidl.md)   
 [includelib](../windows/includelib-cpp.md)   
 [importlib](../windows/importlib.md)   
