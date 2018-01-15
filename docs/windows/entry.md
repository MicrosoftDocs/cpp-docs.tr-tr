---
title: "Giriş | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.entry
dev_langs: C++
helpviewer_keywords: entry attribute
ms.assetid: ba4843e3-d7ad-4b86-9a15-0b4192f0f698
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9ffd90ccdcce39ab73f1c1b550b466541dacf8a1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="entry"></a>giriş
Bir verilen işlevi veya sabit bir modüle DLL'deki giriş noktası belirleyerek belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ entry(  
   id  
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `id`  
 Giriş noktası kimliği.  
  
## <a name="remarks"></a>Açıklamalar  
 **Girişi** C++ özniteliğine sahip ile aynı işlevselliği [girişi](http://msdn.microsoft.com/library/windows/desktop/aa366815) MIDL özniteliği.  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [idl_module](../windows/idl-module.md) bir örnek kullanımı için **girişi**.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|`idl_module`özniteliği|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
