---
title: importidl | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.importidl
dev_langs:
- C++
helpviewer_keywords:
- importidl attribute
ms.assetid: 4b0a4b55-6c57-4e6e-bc7b-a12cc8063941
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f5284c631813271f5682343c74cff693d1ea785e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33877481"
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
 [İçeri aktarma](../windows/import.md)   
 [importlib](../windows/importlib.md)   
 [İçerir](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)   
