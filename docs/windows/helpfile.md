---
title: HelpFile | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.helpfile
dev_langs:
- C++
helpviewer_keywords:
- helpfile attribute
ms.assetid: d75161c1-1363-4019-ae09-e7e3b8a3971e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f4f25a8f3d5cc76d1b2b8d9a3d9996449f449466
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570453"
---
# <a name="helpfile"></a>helpfile
Bir tür kitaplığı için Yardım dosyasına adını ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[ helpfile(  
   "filename"  
) ]  
```  
  
### <a name="parameters"></a>Parametreler  
 *Dosya adı*  
 Yardım konuları içeren dosyanın adı.  
  
## <a name="remarks"></a>Açıklamalar  
 **Helpfile** C++ özniteliği ile aynı işlevlere sahip [helpfile](http://msdn.microsoft.com/library/windows/desktop/aa366853) MIDL özniteliği.  
  
## <a name="example"></a>Örnek  
 Örneğin bakın [Modülü](../windows/module-cpp.md) nasıl kullanılacağına ilişkin bir örnek **helpfile**.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**İçin geçerlidir**|**arabirimi**, **typedef**, **sınıfı**, yöntemi **özelliği**|  
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
 [HelpContext](../windows/helpcontext.md)   
 [helpstring](../windows/helpstring.md)   