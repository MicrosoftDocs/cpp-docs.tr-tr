---
title: "Özel (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.custom
dev_langs: C++
helpviewer_keywords: custom attributes, defining
ms.assetid: 3abac928-4d55-4ea6-8cf6-8427a4ad79f1
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e55fd4ad47470a86a0a3d61cc847c20fb21768e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="custom-c"></a>özel (C++)
Meta veri nesnesi için Tür Kitaplığı'nda tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ custom(  
   uuid,   
   value  
) ];  
```  
  
#### <a name="parameters"></a>Parametreler  
 *UUID*  
 Benzersiz kimliği  
  
 *value*  
 Bir değişken koyabilirsiniz bir değer.  
  
## <a name="remarks"></a>Açıklamalar  
 **Özel** C++ öznitelik türü kitaplığa yerleştirilecek bilgi neden olur. Tür kitaplığından özel değeri okuyan bir aracı gerekir.  
  
 **Özel** özniteliğine sahip ile aynı işlevselliği [özel](http://msdn.microsoft.com/library/windows/desktop/aa366766) MIDL özniteliği.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|Olmayan COM `interface`, **sınıfı**, `enum`s, `idl_module` yöntemleri, arabirim üyeleri, arabirim parametrelerini `typedef`s, **UNION**s, `struct`s|  
|**Yinelenebilir**|Evet|  
|**Gerekli öznitelikler**|**coclass'ı** (sınıf üzerinde kullanıldığında)|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Tek başına öznitelikler](../windows/stand-alone-attributes.md)   
 [TypeDef, Enum, Union ve Struct öznitelikleri](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Parametre öznitelikleri](../windows/parameter-attributes.md)   
 [Yöntem öznitelikleri](../windows/method-attributes.md)   
 [Sınıf öznitelikleri](../windows/class-attributes.md)   
 [Arabirim Öznitelikleri](../windows/interface-attributes.md)   
