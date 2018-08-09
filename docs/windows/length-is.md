---
title: length_is | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.length_is
dev_langs:
- C++
helpviewer_keywords:
- length_is attribute
ms.assetid: 1d99b883-84bb-4b1e-b098-eb780fc94f40
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d30a467bd929c68c35e06861087ec7f47d1f2d51
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40011913"
---
# <a name="lengthis"></a>length_is
Aktarılacak dizi öğelerinin sayısını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
[ length_is(  
   "expression"  
) ]  
```  
  
### <a name="parameters"></a>Parametreler  
 *İfade*  
 Bir veya daha fazla C dili ifadeleri. Boş bağımsız değişken yuvaları izin verilir.  
  
## <a name="remarks"></a>Açıklamalar  
 **Length_is** C++ özniteliği ile aynı işlevlere sahip [length_is](http://msdn.microsoft.com/library/windows/desktop/aa367068) MIDL özniteliği.  
  
## <a name="example"></a>Örnek  
 Bkz: [first_is](../windows/first-is.md) örneği nasıl bir dizinin bir bölümünü belirtin.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**İçin geçerlidir**|İçinde alan **yapı** veya **birleşim**, parametre arabirim, arabirim yöntemi|  
|**Tekrarlanabilir**|Hayır|  
|**Gerekli öznitelikleri**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Daha fazla bilgi için [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [TypeDef, Enum, Union ve Struct öznitelikleri](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Parametre öznitelikleri](../windows/parameter-attributes.md)   
 [first_is](../windows/first-is.md)   
 [max_is](../windows/max-is.md)   
 [last_is](../windows/last-is.md)   
 [size_is](../windows/size-is.md)   