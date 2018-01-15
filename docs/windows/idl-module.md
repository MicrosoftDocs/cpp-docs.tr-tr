---
title: idl_module | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.idl_module
dev_langs: C++
helpviewer_keywords: idl_module attribute
ms.assetid: 3578b337-e38a-4334-b747-15404c02dbc0
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f052692686149b247a50c0d89e77797f4f48fab3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="idlmodule"></a>idl_module
Bir giriş noktası bir .dll dosyasını belirtir.  
  
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
  
#### <a name="parameters"></a>Parametreler  
 **adı**  
 Kullanıcı tanımlı için bir ad .idl dosyasında görünür kod bloğu.  
  
 **dll** (isteğe bağlı)  
 Dışarı aktarma içeren .dll dosyası.  
  
 `uuid`(isteğe bağlı)  
 Benzersiz kimliği  
  
 **HelpString** (isteğe bağlı)  
 Tür kitaplığı tanımlamak için kullanılan bir karakter dizesi.  
  
 **helpstringcontext** (isteğe bağlı)  
 Yardım konusunun .hlp veya .chm dosyasındaki kimliği.  
  
 **HelpContext** (isteğe bağlı)  
 Bu tür kitaplığı Yardım kimliği.  
  
 **Gizli** (isteğe bağlı)  
 Kitaplık görüntülenmesini engeller parametresi. Bkz: [gizli](http://msdn.microsoft.com/library/windows/desktop/aa366861) daha fazla bilgi için MIDL özniteliği.  
  
 ***kısıtlı*** (isteğe bağlı)  
 Kitaplık üyelerini rasgele çağrılamaz. Bkz: [kısıtlı](http://msdn.microsoft.com/library/windows/desktop/aa367157) daha fazla bilgi için MIDL özniteliği.  
  
 *işlev bildirimi*  
 Tanımlayacaksınız işlev.  
  
## <a name="remarks"></a>Açıklamalar  
 `idl_module` C++ öznitelik bir .dll dosyası içeri olanak tanıyan bir .dll dosyasına giriş noktası belirtmenize olanak sağlar.  
  
 **İdl_module** özniteliğine sahip benzer işlevselliği [Modülü](http://msdn.microsoft.com/library/windows/desktop/aa367099) MIDL özniteliği.  
  
 Herhangi bir şey .idl dosya kitaplığını bloğunu DLL giriş noktası koyarak bir .dll dosyasından verebilirsiniz bir COM nesnesinden verebilirsiniz.  
  
 Kullanmalısınız `idl_module` iki adımda. İlk olarak, bir ad/DLL çifti tanımlamanız gerekir. Ardından, kullandığınızda `idl_module` bir giriş noktası belirtmek için adı ve diğer ek öznitelikleri belirtin.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kodu nasıl kullanılacağını gösterir `idl_module` özniteliği:  
  
```  
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
|**Uygulandığı öğe:**|Her yerden|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Tek başına öznitelikler](../windows/stand-alone-attributes.md)   
 [entry](../windows/entry.md)   
