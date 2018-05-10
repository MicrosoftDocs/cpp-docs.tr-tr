---
title: importlib | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.importlib
dev_langs:
- C++
helpviewer_keywords:
- importlib attribute
ms.assetid: f129e459-b8d3-4aca-a0bc-ee53e18b62ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c21b97e50fa03861245a0c0881963387dd8a3102
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
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
 [İçeri aktarma](../windows/import.md)   
 [importidl](../windows/importidl.md)   
 [İçerir](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)