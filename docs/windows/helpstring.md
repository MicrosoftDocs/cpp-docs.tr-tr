---
title: HelpString | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.helpstring
dev_langs: C++
helpviewer_keywords: helpstring attribute [C++]
ms.assetid: 0401e905-a63e-4fad-98d0-d1efea111966
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 27cf95f5017775fbf7a0315341cea19931f64068
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="helpstring"></a>helpstring
Uygulandığı öğe tanımlamak için kullanılan bir karakter dizesini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ helpstring(  
   "string"  
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `string`  
 Yardım dizesi metin.  
  
## <a name="remarks"></a>Açıklamalar  
 **Helpstring** C++ özniteliğine sahip ile aynı işlevselliği [helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856) MIDL özniteliği.  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [defaultvalue](../windows/defaultvalue.md) nasıl kullanılacağına ilişkin bir örnek **helpstring**.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|`interface`, `typedef`, **sınıfı**, yöntemi, özelliği|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Arabirim öznitelikleri](../windows/interface-attributes.md)   
 [Sınıf öznitelikleri](../windows/class-attributes.md)   
 [Yöntem öznitelikleri](../windows/method-attributes.md)   
 [TypeDef, Enum, Union ve Struct öznitelikleri](../windows/typedef-enum-union-and-struct-attributes.md)   
 [HelpFile](../windows/helpfile.md)   
 [HelpContext](../windows/helpcontext.md)   
