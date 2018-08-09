---
title: Nesne (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.object
dev_langs:
- C++
helpviewer_keywords:
- object attribute
ms.assetid: f2d3c231-630d-4b4c-bd15-b1c30df362dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2667c8ecb14e31388737366c4de6c527bdc40f9d
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40012758"
---
# <a name="object-c"></a>nesne (C++)
Özel bir arabirim tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
[object]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bir arabirim tanımı önce geldiği zaman **nesne** C++ özniteliği arabirimi .idl dosyası özel bir arabirim olarak yerleştirilmesini neden olur.  
  
 Nesne ile işaretlenen herhangi bir arabirimde devralmalıdır `IUnknown`. Devralınan taban arabirimlerin herhangi, bu koşul sağlanana `IUnknown`. Temel arabirim devralır, `IUnknown`, derleyici ile işaretlenen arabirim neden olacak **nesne** türetmek için `IUnknown`.  
  
## <a name="example"></a>Örnek  
 Bkz: [nonbrowsable](../windows/nonbrowsable.md) nasıl kullanılacağına ilişkin bir örnek **nesne**.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**İçin geçerlidir**|**interface**|  
|**Tekrarlanabilir**|Hayır|  
|**Gerekli öznitelikleri**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Arabirim öznitelikleri](../windows/interface-attributes.md)   
 [Çift](../windows/dual.md)   
 [Dispinterface](../windows/dispinterface.md)   
 [Özel](../windows/custom-cpp.md)   
 [__interface](../cpp/interface.md)   