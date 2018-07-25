---
title: Alma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.import
dev_langs:
- C++
helpviewer_keywords:
- import attribute
ms.assetid: ebf07cae-39fb-4047-8b57-54af0a9a83de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b371cd1094a49f8a629cb6f8e880fd1210670f91
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33877273"
---
# <a name="import"></a>içeri aktar
, Ana IDL başvuru yapmak istediğinizi tanımlarını içeren başka bir .idl, .odl veya üst bilgi dosyasını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ import(  
   idl_file  
) ];  
```  
  
#### <a name="parameters"></a>Parametreler  
 `idl_file`  
 Geçerli projenin türü kitaplığa içeri aktarılan istediğiniz bir .idl dosyanın adı.  
  
## <a name="remarks"></a>Açıklamalar  
 **Alma** C++ öznitelik neden olan bir `#import` altına yerleştirilecek deyimi `import "docobj.idl"` oluşturulan .idl dosyasındaki deyimi. **Alma** özniteliğine sahip ile aynı işlevselliği [alma](http://msdn.microsoft.com/library/windows/desktop/aa367047) MIDL özniteliği.  
  
 **Alma** özniteliği yalnızca yerleştirir belirtilen dosya projeniz tarafından; oluşturulan .idl dosyasına **alma** özniteliği izin vermez, yapıları belirtilen dosyada kaynak kodundan çağırın. Projenizde.  Yapıları projenizi kaynak kodunda belirtilen dosyada çağırmanıza için ya da kullanın [#import](../preprocessor/hash-import-directive-cpp.md) ve `embedded_idl` özniteliği veya .h dosyayı içerebilir `idl_file`, .h dosya varsa.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod:  
  
```  
// cpp_attr_ref_import.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[import(import.idl)];  
```  
  
 Aşağıdaki kod oluşturulan .idl dosyasındaki üretir:  
  
```  
import "docobj.idl";  
import "import.idl";  
  
[ uuid(EED3644C-8488-3ECD-BA97-147DB3CDB499), version(1.0) ]  
library MyLib {  
   importlib("stdole2.tlb");  
   importlib("olepro32.dll");  
...  
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
 [importidl](../windows/importidl.md)   
 [importlib](../windows/importlib.md)   
 [İçerir](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)   
