---
title: last_is | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.last_is
dev_langs:
- C++
helpviewer_keywords:
- last_is attribute
ms.assetid: 9e045ac0-fa38-4249-af55-67bde5d0a58c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f27c0a12ddf5fe87f7065a16d042bd0afcfc0315
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="lastis"></a>last_is
Aktarılacak son dizi öğesinden dizinini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ last_is(  
   "expression"  
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 *ifade*  
 C dili ifadeleri bir veya daha fazla. Boş bağımsız değişkeni yuvaları izin verilir.  
  
## <a name="remarks"></a>Açıklamalar  
 **Last_is** C++ özniteliğine sahip ile aynı işlevselliği [last_is](http://msdn.microsoft.com/library/windows/desktop/aa367066) MIDL özniteliği.  
  
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
 [length_is](../windows/length-is.md)   
 [size_is](../windows/size-is.md)   
