---
title: importidl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.importidl
dev_langs:
- C++
helpviewer_keywords:
- importidl attribute
ms.assetid: 4b0a4b55-6c57-4e6e-bc7b-a12cc8063941
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cd3fb56898107b1eca7cd30e06d75d253a02655e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="importidl"></a>importidl
Belirtilen .idl dosya oluşturulan .idl dosyasına ekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ importidl(  
   idl_file  
) ];  
```  
  
#### <a name="parameters"></a>Parametreler  
 `idl_file`  
 Uygulamanız için oluşturulacak .idl dosyayla birleştirmek istediğiniz .idl dosyasının adını tanımlar.  
  
## <a name="remarks"></a>Açıklamalar  
 **İmportidl** C++ öznitelik yerleştirir bölüm kitaplığını bloğunu dışında (içinde `idl_file`) programınızın oluşturulan .idl dosya ve kitaplık bölümüne (içinde `idl_file`) programınızın kitaplığı bölümüne oluşturulan .idl dosyası.  
  
 Kullanmak istediğiniz **importidl**, örneğin, bir yandan kodlanmış .idl ile oluşturulan .idl dosyası kullanmak istiyorsanız.  
  
## <a name="example"></a>Örnek  
  
```  
// cpp_attr_ref_importidl.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[importidl("import.idl")];  
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
 [Derleyici öznitelikleri](../windows/compiler-attributes.md)   
 [Tek başına öznitelikler](../windows/stand-alone-attributes.md)   
 [içeri aktarma](../windows/import.md)   
 [importlib](../windows/importlib.md)   
 [içerir](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)   
