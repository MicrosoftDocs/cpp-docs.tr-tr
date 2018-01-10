---
title: length_is | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.length_is
dev_langs: C++
helpviewer_keywords: length_is attribute
ms.assetid: 1d99b883-84bb-4b1e-b098-eb780fc94f40
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a40132e793bc444547eefefa70ed3b146cafadc2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
