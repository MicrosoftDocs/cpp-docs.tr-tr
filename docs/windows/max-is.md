---
title: max_is | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.max_is
dev_langs:
- C++
helpviewer_keywords:
- max_is attribute
ms.assetid: 7c851f5c-6649-4d77-a792-247c37d8f560
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2799039aa2c198bcea3784876d8299fcaec59b20
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40012455"
---
# <a name="maxis"></a>max_is
Geçerli dizi dizini için maksimum değeri atar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
[ max_is(  
   "expression"  
) ]  
```  
  
### <a name="parameters"></a>Parametreler  
 *İfade*  
 Bir veya daha fazla C dili ifadeleri. Boş bağımsız değişken yuvaları izin verilir.  
  
## <a name="remarks"></a>Açıklamalar  
 **Max_is** C++ özniteliği ile aynı işlevlere sahip [max_is](http://msdn.microsoft.com/library/windows/desktop/aa367074) MIDL özniteliği.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**İçin geçerlidir**|İçinde alan **yapı** veya **birleşim**, parametre arabirim, arabirim yöntemi|  
|**Tekrarlanabilir**|Hayır|  
|**Gerekli öznitelikleri**|Yok.|  
|**Geçersiz öznitelikler**|**size_is**|  
  
 Daha fazla bilgi için [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="example"></a>Örnek  
 Bkz: [first_is](../windows/first-is.md) örneği nasıl bir dizinin bir bölümünü belirtin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [TypeDef, Enum, Union ve Struct öznitelikleri](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Parametre öznitelikleri](../windows/parameter-attributes.md)   
 [first_is](../windows/first-is.md)   
 [last_is](../windows/last-is.md)   
 [length_is](../windows/length-is.md)   
 [size_is](../windows/size-is.md)   