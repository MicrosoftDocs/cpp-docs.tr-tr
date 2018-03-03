---
title: no_injected_text | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.no_injected_text
dev_langs:
- C++
helpviewer_keywords:
- no_injected_text attribute
ms.assetid: 5256f808-e41e-4f4a-9ea5-e447919f5696
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8c74d3134b5381be4ec330742726b26fea6155da
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="noinjectedtext"></a>no_injected_text
Özellik kullanımı sonucunda kodu injecting derleyici engeller.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ no_injected_text(  
   boolean  
) ];  
```  
  
#### <a name="parameters"></a>Parametreler  
 `boolean`(isteğe bağlı)  
 **doğru** eklenen, kod istiyorsanız **false** eklenemeyebilir kodu izin vermek için. **doğru** varsayılandır.  
  
## <a name="remarks"></a>Açıklamalar  
 En yaygın kullanımı **no_injected_text** C++ özniteliktir [/Fx](../build/reference/fx-merge-injected-code.md) ekler derleyici seçeneği **no_injected_text** .mrg dosyasına özniteliği.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|Her yerden|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Öznitelikleri](../windows/compiler-attributes.md)   
