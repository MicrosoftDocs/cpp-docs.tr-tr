---
title: "Sürüm (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.version
dev_langs: C++
helpviewer_keywords:
- version attribute
- version information, version attribute
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 757ab7a6d2c8b846a51da359c4b8dc5a72c6e9e8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
|**Gerekli öznitelikler**|**coclass'ı**|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici öznitelikleri](../windows/compiler-attributes.md)   
 [Sınıf öznitelikleri](../windows/class-attributes.md)   
