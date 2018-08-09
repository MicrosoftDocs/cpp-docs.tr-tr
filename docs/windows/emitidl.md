---
title: emitidl | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.emitidl
dev_langs:
- C++
helpviewer_keywords:
- emitidl attribute
ms.assetid: 85b80c56-578e-4392-ac03-8443c74ebb7d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5d508c6196ad9b9f32b4bcb0704272a500d0e952
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39643049"
---
# <a name="emitidl"></a>emitidl
Tüm sonraki IDL öznitelikleri işlenir ve oluşturulan .idl dosyasında yerleştirilmiş olup olmadığını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
[ emitidl(state, defaultimports=boolean) ];
```  
  
### <a name="parameters"></a>Parametreler  
*durumu*  
Bu değerlerden biri: `true`, `false`, `forced`, `restricted`, `push`, veya `pop`.  
  
-   Varsa `true`, bir kaynak kodu dosyasında karşılaşılan kategori IDL öznitelikleri oluşturulan .idl dosyasında yerleştirilir. İçin varsayılan ayar budur **emitidl**.  
  
-   Varsa `false`, bir kaynak kodu dosyasında karşılaşılan kategori IDL öznitelikleri oluşturulan .idl dosyasına yerleştirilmez.  
  
-   Varsa `restricted`, IDL öznitelikleri dosyasındaki olmasını sağlayan bir [Modülü](../windows/module-cpp.md) özniteliği. Derleyici bir .idl dosyası oluşturmaz.  
  
-   Varsa `forced`, bir sonraki geçersiz kılar `restricted` sahip için dosya gerektirmiyor özniteliği, bir `module` IDL varsa özniteliği dosyasında öznitelikleri.  
  
-   `push` Geçerli kaydetmenizi sağlayan **emitidl** ayarları bir iç **emitidl** yığını ve `pop` , ayarlamanıza imkan sağlar **emitidl** ne olursa olsun değer iç üstünde olduğu için **emitidl** yığını.  
  
`defaultimports=`*Boole* \(isteğe bağlı)  
-   Varsa *Boole* olduğu **true**, docobj.idl oluşturulan .idl dosyasına aktarılır. Ayrıca, bir .idl dosyası ile aynı adı taşıyan bir .h dosyası varsa `#include` kaynak kodu .h dosyası ile aynı dizinde bulunan ve ardından söz konusu .idl dosyası için bir içeri aktarma deyimi oluşturulan .idl dosyası içerir.  
  
-   Varsa *Boole* olduğu **false**, docobj.idl oluşturulan .idl dosyasına alınmadı. .İdl dosyaları ile açıkça içeri aktarmanız gerekir [alma](../windows/import.md).  
  
## <a name="remarks"></a>Açıklamalar  
Sonra **emitidl** C++ öznitelik, bir kaynak kodu dosyasında karşılaşıldığında, IDL kategori öznitelikler oluşturulan .idl dosyasında yerleştirilir. Yoksa hiçbir **emitidl** özniteliği, kaynak kod dosyasında IDL öznitelikleri oluşturulan .idl dosyasının çıkarılır.  
  
Birden çok olması mümkündür **emitidl** kaynak kodu dosyasında öznitelikleri. Varsa `[emitidl(false)];` sonraki olmadan bir dosya ile karşılaşılırsa `[emitidl(true)];`, sonra oluşturulan .idl dosyasına özniteliklere işlenir.  
  
Derleyici, yeni bir dosya karşılaştığında her zaman **emitidl** örtük olarak ayarlandığında **true**.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**İçin geçerlidir**|Her yerde|  
|**Tekrarlanabilir**|Hayır|  
|**Gerekli öznitelikleri**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
Daha fazla bilgi için [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[Derleyici öznitelikleri](../windows/compiler-attributes.md)   
[Tek başına öznitelikler](../windows/stand-alone-attributes.md)   
[Öznitelikleri örnekleri](http://msdn.microsoft.com/en-us/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)