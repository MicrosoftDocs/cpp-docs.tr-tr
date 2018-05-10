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
ms.openlocfilehash: 43da63d75d3541915eba3e561ee08fe1048fa579
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
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
|**Uygulandığı öğe:**|**sınıf**, `struct`|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|**coclass**|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici öznitelikleri](../windows/compiler-attributes.md)   
 [Sınıf Öznitelikleri](../windows/class-attributes.md)   
