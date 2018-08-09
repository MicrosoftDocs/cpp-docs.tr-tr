---
title: Sürüm (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.version
dev_langs:
- C++
helpviewer_keywords:
- version attribute
- version information, version attribute
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2c2d0c72ffbb805b526429562a5f39a09285b70f
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39642285"
---
# <a name="version-c"></a>sürüm (C++)
Bir sınıfın birden çok sürümü arasında belirli bir sürümünü tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[ version(  
   "version"  
) ]  
```  
  
### <a name="parameters"></a>Parametreler  
 *Sürüm*  
 Sürüm numarasını `coclass`. Belirtilmezse, 1.0 .idl dosyasında yer alır.  
  
## <a name="remarks"></a>Açıklamalar  
 **Sürüm** C++ özniteliği ile aynı işlevlere sahip [sürüm](http://msdn.microsoft.com/library/windows/desktop/aa367306) MIDL özniteliği ve oluşturulan .idl dosyasına üzerinden geçirilir.  
  
## <a name="example"></a>Örnek  
 Bkz: [bağlanabilir](../windows/bindable.md) örnek kullanımını örneğin **sürüm**.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**İçin geçerlidir**|**sınıf**, **yapısı**|  
|**Tekrarlanabilir**|Hayır|  
|**Gerekli öznitelikleri**|**coclass**|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici öznitelikleri](../windows/compiler-attributes.md)   
 [Sınıf Öznitelikleri](../windows/class-attributes.md)   