---
title: "Varsayılan (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.default
dev_langs: C++
helpviewer_keywords:
- default attribute
- attributes [C#], default attribute
- defaults, default attribute
ms.assetid: 0cdca716-1ba8-46d7-9399-167e55492870
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6b24b0ed9b8e547a52388b6f93a4955da782331b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="default-c"></a>default (C++)
Özel veya görüntüleme arabirimi coclass'ı içinde tanımlanan varsayılan programlama arabirimi temsil ettiğini gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ default(  
   interface1,  
   interface2  
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 *interface1*  
 Bir nesne oluşturma komut dosyası ortamlar için kullanıma sunulacaktır varsayılan arabirimi ile tanımlanmış sınıfı temelinde **varsayılan** özniteliği.  
  
 Varsayılan arabirim belirtilirse, birinci denetimine arabirimi varsayılan olarak kullanılır.  
  
 *interface2*(isteğe bağlı)  
 Varsayılan kaynak arabirimi. Bu arabirimle belirtmeniz gerekir [kaynak](../windows/source-cpp.md) özniteliği.  
  
 Varsayılan kaynak arabirimi olmadan belirtilirse, ilk kaynak arabirimi varsayılan olarak kullanılır.  
  
## <a name="remarks"></a>Açıklamalar  
 **Varsayılan** C++ özniteliğine sahip ile aynı işlevselliği [varsayılan](http://msdn.microsoft.com/library/windows/desktop/aa366787) MIDL özniteliği. **Varsayılan** özniteliği ile kullanılan de [durumda](../windows/case-cpp.md) özniteliği.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kodda gösterildiği nasıl **varsayılan** bir coclass'ı tanımını belirtmek için kullanılan **ICustomDispatch** varsayılan programlama arabirimi olarak:  
  
```  
// cpp_attr_ref_default.cpp  
// compile with: /LD  
#include "windows.h"  
[module(name="MyLibrary")];  
  
[object, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]  
__interface ICustom {  
   HRESULT Custom([in] long l, [out, retval] long *pLong);  
};  
  
[dual, uuid("9E66A291-4365-11D2-A997-00C04FA37DDB")]   
__interface IDual {  
   HRESULT Dual([in] long l, [out, retval] long *pLong);  
};  
  
[object, uuid("9E66A293-4365-11D2-A997-00C04FA37DDB")]  
__interface ICustomDispatch : public IDispatch {  
   HRESULT Dispatch([in] long l, [out, retval] long *pLong);  
};  
  
[   coclass,  
   default(ICustomDispatch),   
   source(IDual),  
   uuid("9E66A294-4365-11D2-A997-00C04FA37DDB")  
]  
class CClass : public ICustom, public IDual, public ICustomDispatch {  
   HRESULT Custom(long l, long *pLong) { return(S_OK); }  
   HRESULT Dual(long l, long *pLong) { return(S_OK); }  
   HRESULT Dispatch(long l, long *pLong) { return(S_OK); }  
};  
  
int main() {  
#if 0 // Can't instantiate without implementations of IUnknown/IDispatch  
   CClass *pClass = new CClass;  
  
   long llong;  
  
   pClass->custom(1, &llong);  
   pClass->dual(1, &llong);  
   pClass->dispinterface(1, &llong);  
   pClass->dispatch(1, &llong);  
  
   delete pClass;  
#endif  
   return(0);  
}  
```  
  
 [Kaynak](../windows/source-cpp.md) de öznitelikle nasıl kullanılacağına ilişkin bir örnek **varsayılan**.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|**sınıf**, `struct`, veri üyesi|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|**coclass'ı** (uygulandığında **sınıfı** veya `struct`)|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Sınıf öznitelikleri](../windows/class-attributes.md)   
 [coclass](../windows/coclass.md)   
