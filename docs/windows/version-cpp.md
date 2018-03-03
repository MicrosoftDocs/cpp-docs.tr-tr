---
title: "Sürüm (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.version
dev_langs:
- C++
helpviewer_keywords:
- version attribute
- version information, version attribute
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: db6c31df932890799f68e2ae466b0a927f0f999f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="version-c"></a>sürüm (C++)
Bir sınıfın birden çok sürümü arasında belirli bir sürümünü tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ version(  
   "version"  
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Sürüm*  
 Coclass'ı sürüm numarası. Belirtilmezse, 1.0 .idl dosyasında yer alır.  
  
## <a name="remarks"></a>Açıklamalar  
 **Sürüm** C++ özniteliğine sahip ile aynı işlevselliği [sürüm](http://msdn.microsoft.com/library/windows/desktop/aa367306) MIDL özniteliği ve oluşturulan .idl dosyasına geçirilir.  
  
## <a name="example"></a>Örnek  
 Bkz: [bağlanabilirse](../windows/bindable.md) bir örnek kullanımı, örneğin **sürüm**.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|**sınıf**,`struct`|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|**coclass**|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici öznitelikleri](../windows/compiler-attributes.md)   
 [Sınıf Öznitelikleri](../windows/class-attributes.md)   
