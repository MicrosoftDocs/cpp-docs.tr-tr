---
title: HelpContext | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.helpcontext
dev_langs: C++
helpviewer_keywords: helpcontext attribute
ms.assetid: 6fbb022d-a4b7-4989-a02f-7f18a9b0ad96
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 46611a2cd25f6154d183f44da0c8333471ea2ae6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="helpcontext"></a>helpcontext
Kullanıcı görünümü öğeyle ilgili bilgi bu Yardım dosyasındaki olanak sağlayan bir içerik Kimliğini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ helpcontext(  
   id  
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `id`  
 Yardım konusunun bağlam kimliği. Bkz: [HTML Yardımı: Context-Sensitive yardımcı olmak için programlarınızı](../mfc/html-help-context-sensitive-help-for-your-programs.md) bağlamı kimlikleri hakkında daha fazla bilgi için.  
  
## <a name="remarks"></a>Açıklamalar  
 **Helpcontext** C++ özniteliğine sahip ile aynı işlevselliği [helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851) MIDL özniteliği.  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [defaultvalue](../windows/defaultvalue.md) nasıl kullanılacağına ilişkin bir örnek **helpcontext**.  
  
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
 [HelpString](../windows/helpstring.md)   
