---
title: ıncludelıb (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.includelib
dev_langs:
- C++
helpviewer_keywords:
- includelib attribute
ms.assetid: cd90ea6e-5ae8-4f11-b8d1-662db95412b2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 252a5d953dd05edc494daf8c4a45322d5511f979
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878898"
---
# <a name="includelib-c"></a>includelib (C++)
Oluşturulan .idl dosyasında dahil edilecek bir .idl veya .h dosyası neden olur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ includelib(  
   name.idl  
) ];  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Name.idl*  
 Oluşturulan .idl dosyanın bir parçası olarak dahil istediğiniz .idl dosyasının adı.  
  
## <a name="remarks"></a>Açıklamalar  
 `includelib` C++ öznitelik neden sonra oluşturulan .idl dosyasında dahil edilecek bir .idl veya .h dosyası `importlib` deyimi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod bir .cpp dosyasında gösterilir:  
  
```  
// cpp_attr_ref_includelib.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[includelib("includelib.idl")];  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|Her yerden|  
|**Yinelenebilir**|Evet|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Tek başına öznitelikler](../windows/stand-alone-attributes.md)   
 [İçeri aktarma](../windows/import.md)   
 [importidl](../windows/importidl.md)   
 [İçerir](../windows/include-cpp.md)   
 [importlib](../windows/importlib.md)   
