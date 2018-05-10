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
ms.openlocfilehash: 6d41c2c4747f69b5ddfae4cd5863c072cd2316ec
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="lengthis"></a>length_is
Aktarılacak dizi öğelerinin sayısını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ length_is(  
   "expression"  
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 *ifade*  
 C dili ifadeleri bir veya daha fazla. Boş bağımsız değişkeni yuvaları izin verilir.  
  
## <a name="remarks"></a>Açıklamalar  
 **Length_is** C++ özniteliğine sahip ile aynı işlevselliği [length_is](http://msdn.microsoft.com/library/windows/desktop/aa367068) MIDL özniteliği.  
  
## <a name="example"></a>Örnek  
 Bkz: [first_is](../windows/first-is.md) bir dizi bir bölümünü belirleme konusunda bir örneği.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|İçinde alan `struct` veya **UNION**, parametre arabirim, arabirim yöntemi|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [TypeDef, Enum, Union ve Struct öznitelikleri](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Parametre öznitelikleri](../windows/parameter-attributes.md)   
 [first_is](../windows/first-is.md)   
 [max_is](../windows/max-is.md)   
 [last_is](../windows/last-is.md)   
 [size_is](../windows/size-is.md)   
