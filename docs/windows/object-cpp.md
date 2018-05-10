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
ms.openlocfilehash: 601d67fb48f0ae826474d33e7dca0fbffff9478c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="object-c"></a>nesne (C++)
Özel bir arabirim tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
[object]  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Arabirim tanımı, önceki zaman **nesne** C++ öznitelik .idl dosyası özel bir arabirim olarak yerleştirilecek arabirimi neden olur.  
  
 Nesnesi ile işaretlenen herhangi bir arabirim öğesinden devralmalıdır **IUnknown**. Bu koşul herhangi temel arabirimlerin devralınmalıdır varsa sağlanırsa **IUnknown**. Temel arabirim devralması durumunda **IUnknown**, derleyici ile işaretlenen arabirimi neden olacak **nesne** türetmek **IUnknown**.  
  
## <a name="example"></a>Örnek  
 Bkz: [nonbrowsable](../windows/nonbrowsable.md) nasıl kullanılacağına ilişkin bir örnek **nesne**.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|`interface`|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Arabirim öznitelikleri](../windows/interface-attributes.md)   
 [Çift](../windows/dual.md)   
 [Görüntüleme arabirimi](../windows/dispinterface.md)   
 [Özel](../windows/custom-cpp.md)   
 [__interface](../cpp/interface.md)   
