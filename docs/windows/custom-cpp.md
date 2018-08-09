---
title: Özel (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.custom
dev_langs:
- C++
helpviewer_keywords:
- custom attributes, defining
ms.assetid: 3abac928-4d55-4ea6-8cf6-8427a4ad79f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2c0f4f04adb9ddc847b1c22485d10512a9d684d0
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39651901"
---
# <a name="custom-c"></a>özel (C++)
Bir nesne için meta verileri tür kitaplığındaki tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
[ custom(  
   uuid,   
   value  
) ];  
```  
  
### <a name="parameters"></a>Parametreler  
 *uuid*  
 Benzersiz kimliği  
  
 *value*  
 Bir değişken koyabilirsiniz bir değer.  
  
## <a name="remarks"></a>Açıklamalar  
 **Özel** C++ özniteliği tür kitaplığına yerleştirilecek bilgi neden olur. Tür kitaplığından özel değeri okuyan bir aracı gerekir.  
  
 **Özel** özniteliği ile aynı işlevlere sahip [özel](http://msdn.microsoft.com/library/windows/desktop/aa366766) MIDL özniteliği.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**İçin geçerlidir**|COM olmayan **arabirimi**, **sınıfı**, **enum**s, `idl_module` yöntemleri, arabirim üyeleri, arabirim parametrelerini **typedef**s, **birleşim**s, **yapı**s|  
|**Tekrarlanabilir**|Evet|  
|**Gerekli öznitelikleri**|**coclass'ı** (sınıfı kullanıldığında)|  
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