---
title: importlib | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.importlib
dev_langs: C++
helpviewer_keywords: importlib attribute
ms.assetid: f129e459-b8d3-4aca-a0bc-ee53e18b62ed
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7c62db5b1e10f115a57da1ea00cd87760b96a71f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="importlib"></a>importlib
Zaten başka bir tür kitaplığı oluşturulan tür kitaplığı kullanılabilir içine derlenmiştir türleri sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ importlib(  
   "tlb_file"  
) ];  
```  
  
#### <a name="parameters"></a>Parametreler  
 *tlb_file*  
 Geçerli projenin türü kitaplığa içeri aktarılan istediğiniz tırnak, bir .tlb dosyası adı.  
  
## <a name="remarks"></a>Açıklamalar  
 **İmportlib** C++ öznitelik neden olan bir `importlib` oluşturulan .idl dosya kitaplığını bloğunu yerleştirilecek deyimi. **İmportlib** özniteliğine sahip ile aynı işlevselliği [importlib](http://msdn.microsoft.com/library/windows/desktop/aa367050) MIDL özniteliği.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği nasıl kullanılacağını gösterir **importlib**:  
  
```  
// cpp_attr_ref_importlib.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[importlib("importlib.tlb")];  
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
 [Derleyici öznitelikleri](../windows/compiler-attributes.md)   
 [Tek başına öznitelikler](../windows/stand-alone-attributes.md)   
 [içeri aktarma](../windows/import.md)   
 [importidl](../windows/importidl.md)   
 [içerir](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)