---
title: "ıncludelıb (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.includelib
dev_langs: C++
helpviewer_keywords: includelib attribute
ms.assetid: cd90ea6e-5ae8-4f11-b8d1-662db95412b2
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 31b9abdb8795d5814afe73fd7d48fb0e62ac8802
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [içeri aktarma](../windows/import.md)   
 [importidl](../windows/importidl.md)   
 [içerir](../windows/include-cpp.md)   
 [importlib](../windows/importlib.md)   
