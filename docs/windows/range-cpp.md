---
title: "Aralık (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.range
dev_langs: C++
helpviewer_keywords: range attribute
ms.assetid: f352f79e-ecb3-4cdd-9cdd-8406ef473594
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a43ad22484ec8502c66c16caa40933bf8f422df9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="range-c"></a>aralık (C++)
Bağımsız değişken veya değerleri çalışma zamanında ayarlanır alanları için izin verilen değer aralığı belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ range(  
   low,   
   high  
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 *düşük*  
 Düşük aralık değeri.  
  
 *yüksek*  
 Yüksek aralık değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 **Aralığı** C++ özniteliğine sahip ile aynı işlevselliği [aralığı](http://msdn.microsoft.com/library/windows/desktop/aa367151) MIDL özniteliği.  
  
## <a name="example"></a>Örnek  
  
```  
// cpp_attr_ref_range.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLib")];  
  
[object, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]  
__interface ICustom {  
   HRESULT Custom([in] long l, [out, retval] long *pLong);  
   HRESULT length_is1([in, range(0, 999)] long f, [in, length_is(f)] char array[10]);  
   HRESULT length_is2([in, range(-99, -1)] long f, [in, length_is("f"), size_is(10)] char *array);  
};  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|Arabirim yöntemini, arabirim parametresi|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Yöntem öznitelikleri](../windows/method-attributes.md)   
 [Parametre öznitelikleri](../windows/parameter-attributes.md)   
 [Veri üyesi öznitelikleri](../windows/data-member-attributes.md)   
