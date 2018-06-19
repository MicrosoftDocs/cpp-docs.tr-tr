---
title: cpp_quote | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.cpp_quote
dev_langs:
- C++
helpviewer_keywords:
- cpp_quote attribute
ms.assetid: f75327ff-42bd-498b-9177-7ffa25427e1f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 38ecabcde55f49687abf7caff66fb2c316fab0fe
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33871168"
---
# <a name="cppquote"></a>cpp_quote
Belirtilen dize tırnak karakteri olmadan oluşturulan .idl dosyasına yayar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ cpp_quote(  
   "statement"  
) ];  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Deyimi*  
 Bir C yönergesi.  
  
## <a name="remarks"></a>Açıklamalar  
 **Cpp_quote** C++ özniteliktir .idl dosyasında önişlemci yönergesi put istediğinizde kullanışlıdır.  
  
 Aynı zamanda **cpp_quote** ve MIDL derleme bir parçası olarak bir .h dosyası oluşturun. C++ IDL öznitelikleri kullanan, ancak bazı görev için bu dosyayı kullanamazsınız C++ üstbilgi dosyası varsa, örneğin, daha sonra kullanabilmek için bir MIDL oluşturulan .h dosyası oluşturmak üzere derleyebilirsiniz.  
  
 **Cpp_quote** özniteliğine sahip ile aynı işlevselliği [cpp_quote](http://msdn.microsoft.com/library/windows/desktop/aa366765) MIDL özniteliği.  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [çift](../windows/dual.md) bir örnek için nasıl kullanılacağını kullanmak **cpp_quote**.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|Her yerden|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Tek Başına Öznitelikler](../windows/stand-alone-attributes.md)   
