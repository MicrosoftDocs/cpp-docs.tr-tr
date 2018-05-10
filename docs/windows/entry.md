---
title: Giriş | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.entry
dev_langs:
- C++
helpviewer_keywords:
- entry attribute
ms.assetid: ba4843e3-d7ad-4b86-9a15-0b4192f0f698
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: db90390be5313ddbea1103105f47b55fe9e23d62
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
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
|**Uygulandığı öğe:**|`idl_module` Özniteliği|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
