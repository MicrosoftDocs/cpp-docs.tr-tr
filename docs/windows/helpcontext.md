---
title: HelpContext | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.helpcontext
dev_langs:
- C++
helpviewer_keywords:
- helpcontext attribute
ms.assetid: 6fbb022d-a4b7-4989-a02f-7f18a9b0ad96
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2089bca316fb37304765ac14475b73cadaf79342
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39571366"
---
# <a name="helpcontext"></a>helpcontext
Kullanıcı Yardım dosyasında bu öğe hakkındaki bilgileri görüntüleme sağlayan bir bağlam kimliği belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[ helpcontext(  
   id  
) ]  
```  
  
### <a name="parameters"></a>Parametreler  
 *id*  
 Yardım içeriği kimliği. Bkz: [HTML Help: Context-Sensitive Help for Your Programs](../mfc/html-help-context-sensitive-help-for-your-programs.md) bağlam kimlikleri hakkında daha fazla bilgi için.  
  
## <a name="remarks"></a>Açıklamalar  
 **Helpcontext** C++ özniteliği ile aynı işlevlere sahip [helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851) MIDL özniteliği.  
  
## <a name="example"></a>Örnek  
 Örneğin bakın [defaultvalue](../windows/defaultvalue.md) nasıl kullanılacağına ilişkin bir örnek **helpcontext**.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**İçin geçerlidir**|**arabirimi**, **typedef**, **sınıfı**, yöntem, özellik|  
|**Tekrarlanabilir**|Hayır|  
|**Gerekli öznitelikleri**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Daha fazla bilgi için [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Arabirim öznitelikleri](../windows/interface-attributes.md)   
 [Sınıf öznitelikleri](../windows/class-attributes.md)   
 [Yöntem öznitelikleri](../windows/method-attributes.md)   
 [TypeDef, Enum, Union ve Struct öznitelikleri](../windows/typedef-enum-union-and-struct-attributes.md)   
 [HelpFile](../windows/helpfile.md)   
 [helpstring](../windows/helpstring.md)   