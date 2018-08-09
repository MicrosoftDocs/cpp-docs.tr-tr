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
ms.openlocfilehash: 1de680b2598a9439338986c283a4041482642fa0
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40015764"
---
# <a name="importidl"></a>importidl
Belirtilen .idl dosyası oluşturulan .idl dosyasına ekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
[ importidl(  
   idl_file  
) ];  
```  
  
### <a name="parameters"></a>Parametreler  
 *idl_file*  
 Uygulamanız için oluşturulacak .idl dosyası ile birleştirmek istediğiniz .idl dosyasının adını tanımlar.  
  
## <a name="remarks"></a>Açıklamalar  
 **İmportidl** C++ özniteliği yerleştirir kitaplığı bloğu dışında bölümü (içinde *idl_file*) programınızın oluşturulan .idl dosyasının ve kitaplık bölümü (içinde *idl_file*) kitaplığa programınızın bölümünü .idl dosyası oluşturulur.  
  
 Kullanmak istediğiniz **importidl**, örneğin, bir .idl el kodlanmış ile oluşturulan .idl dosyası kullanmak istiyorsanız.  
  
## <a name="example"></a>Örnek  
  
```cpp  
// cpp_attr_ref_importidl.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[importidl("import.idl")];  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**İçin geçerlidir**|Her yerde|  
|**Tekrarlanabilir**|Hayır|  
|**Gerekli öznitelikleri**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Daha fazla bilgi için [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici öznitelikleri](../windows/compiler-attributes.md)   
 [Tek başına öznitelikler](../windows/stand-alone-attributes.md)   
 [içeri aktarma](../windows/import.md)   
 [importlib](../windows/importlib.md)   
 [İçerir](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)   