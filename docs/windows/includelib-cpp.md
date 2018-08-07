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
ms.openlocfilehash: e10ab341dc4c90a26315ea5e30f03bc71e628b64
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39603387"
---
# <a name="includelib-c"></a>includelib (C++)
Oluşturulan .idl dosyasına eklenecek bir .idl veya .h dosyası neden olur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[ includelib(  
   name.idl  
) ];  
```  
  
### <a name="parameters"></a>Parametreler  
 *Name.idl*  
 Oluşturulan .idl dosyasının bir parçası olarak dahil istediğiniz .idl dosyasının adı.  
  
## <a name="remarks"></a>Açıklamalar  
 **İncludelib** C++ öznitelik neden olur, sonra oluşturulan .idl dosyasına eklenecek bir .idl veya .h dosyası `importlib` deyimi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kodu, .cpp dosyasında gösterilir:  
  
```cpp  
// cpp_attr_ref_includelib.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[includelib("includelib.idl")];  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**İçin geçerlidir**|Her yerde|  
|**Tekrarlanabilir**|Evet|  
|**Gerekli öznitelikleri**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Daha fazla bilgi için [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Tek başına öznitelikler](../windows/stand-alone-attributes.md)   
 [içeri aktarma](../windows/import.md)   
 [importidl](../windows/importidl.md)   
 [İçerir](../windows/include-cpp.md)   
 [importlib](../windows/importlib.md)   