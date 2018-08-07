---
title: idl_module | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.idl_module
dev_langs:
- C++
helpviewer_keywords:
- idl_module attribute
ms.assetid: 3578b337-e38a-4334-b747-15404c02dbc0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bfda47ced14d7c112d27d0036b4d636e32c91907
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39607566"
---
# <a name="idlmodule"></a>idl_module
Bir .dll dosyasına bir giriş noktası belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[ idl_module (   
   name=module_name,   
   dllname=dll,   
   uuid="uuid",   
   helpstring="help text",   
   helpstringcontext=helpcontextID,   
   helpcontext=helpcontext,   
   hidden,   
   restricted  
) ]  
function declaration  
```  
  
### <a name="parameters"></a>Parametreler  
 *Adı*  
 Kullanıcı tanımlı bir ad .idl dosyasında görünür kod bloğu için.  
  
 *dll* (isteğe bağlı)  
 Dışarı aktarma içeren .dll dosyası.  
  
 *uuid* (isteğe bağlı)  
 Benzersiz kimliği  
  
 *HelpString* (isteğe bağlı)  
 Tür kitaplığını açıklamak için kullanılan bir karakter dizesi.  
  
 *helpstringcontext* (isteğe bağlı)  
 Bir Yardım konusu .hlp veya .chm dosyasındaki kimliği.  
  
 *HelpContext* (isteğe bağlı)  
 Bu tür kitaplığı Yardım kimliği.  
  
 *Gizli* (isteğe bağlı)  
 Kitaplık görüntülenmesini engeller. bir parametre. Bkz: [gizli](http://msdn.microsoft.com/library/windows/desktop/aa366861) daha fazla bilgi için MIDL özniteliği.  
  
 *kısıtlı* (isteğe bağlı)  
 Kitaplık üyelerini rasgele çağrılamaz. Bkz: [kısıtlı](http://msdn.microsoft.com/library/windows/desktop/aa367157) daha fazla bilgi için MIDL özniteliği.  
  
 *işlev bildirimi*  
 Tanımladığınız bir işlev.  
  
## <a name="remarks"></a>Açıklamalar  
 **İdl_module** C++ özniteliği bir .dll dosyasından almanızı sağlayan bir .dll dosyası içinde giriş noktasını belirtmenize olanak sağlar.  
  
 **İdl_module** özniteliğine sahip benzer işlevselliği [Modülü](http://msdn.microsoft.com/library/windows/desktop/aa367099) MIDL özniteliği.  
  
 Herhangi bir COM nesnesinden bir .idl dosyası kitaplığı bloğu içinde bir DLL giriş noktası koyarak bir .dll dosyasından dışarı aktarabilirsiniz verebilirsiniz.  
  
 Kullanmalısınız **idl_module** iki adımda. İlk olarak, bir ad/DLL çifti tanımlamanız gerekir. Ardından kullandığınızda **idl_module** bir giriş noktası belirtmek için adı ve diğer ek öznitelikleri belirtin.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod nasıl kullanılacağını gösterir **idl_module** özniteliği:  
  
```cpp  
// cpp_attr_ref_idl_module.cpp  
// compile with: /LD  
[idl_quote("midl_pragma warning(disable:2461)")];  
[module(name="MyLibrary"), idl_module(name="MyLib", dllname="xxx.dll")];  
[idl_module(name="MyLib"), entry(4), usesgetlasterror]  
void FuncName(int i);  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**İçin geçerlidir**|Her yerde|  
|**Tekrarlanabilir**|Hayır|  
|**Gerekli öznitelikleri**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Daha fazla bilgi için [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Tek başına öznitelikler](../windows/stand-alone-attributes.md)   
 [entry](../windows/entry.md)   