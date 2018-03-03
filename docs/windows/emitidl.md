---
title: emitidl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.emitidl
dev_langs:
- C++
helpviewer_keywords:
- emitidl attribute
ms.assetid: 85b80c56-578e-4392-ac03-8443c74ebb7d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 55fc74eef3d2ead7312f7dca46f20c3a1ed7ba91
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="emitidl"></a>emitidl
Tüm sonraki IDL öznitelikleri işlenir ve oluşturulan .idl dosyasında yerleştirilmiş olup olmadığını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
[ emitidl(state, defaultimports=boolean) ];
```  
  
### <a name="parameters"></a>Parametreler  
*durumu*  
Bu değerlerden birini: **true**, **false**, **zorunlu**, **kısıtlı**, **itme**, veya **pop**.  
  
-   Varsa **doğru**, bir kaynak kodu dosyasına karşılaştı IDL kategori öznitelikleri oluşturulan .idl dosyasında yerleştirilir. İçin varsayılan ayar budur **emitidl**.  
  
-   Varsa **yanlış**, bir kaynak kodu dosyasına karşılaştı IDL kategori öznitelikleri oluşturulan .idl dosyasında yerleştirilmez.  
  
-   Varsa **kısıtlı**, IDL öznitelikleri dosyasındaki olmasını sağlayan bir [Modülü](../windows/module-cpp.md) özniteliği. Derleyici .idl dosya oluşturmaz.  
  
-   Varsa **zorunlu**, bir sonraki geçersiz kılar **kısıtlı** sağlamak için bir dosya gerekli öznitelik bir **Modülü** IDL varsa özniteliği dosyasında öznitelikleri.  
  
-   **anında iletme** geçerli kaydetmenizi sağlayan **emitidl** iç ayarlar **emitidl** yığınının ve **pop** , ayarlamanıza imkan sağlar **emitidl**iç en üstünde ne olursa olsun değer için **emitidl** yığını.  
  
`defaultimports=`*Boolean* \(isteğe bağlı)  
-   Varsa *boolean* olan **doğru**, docobj.idl oluşturulan .idl dosyasına aktarılır. Ayrıca, bir .h aynı ada sahip bir .idl dosya dosyası ise `#include` kaynak kodu .h dosyası ile aynı dizinde bulunan ve ardından bu .idl dosyası için bir içeri aktarma deyimini oluşturulan .idl dosyası içerir.  
  
-   Varsa *boolean* olan **yanlış**, oluşturulan .idl dosyasına docobj.idl içe değil. .İdl dosyaları ile açıkça aktarmalısınız [alma](../windows/import.md).  
  
## <a name="remarks"></a>Açıklamalar  
Sonra **emitidl** bir kaynak kodu dosyasına C++ özniteliği ile karşılaşıldı, IDL kategori öznitelikleri oluşturulan .idl dosyasında yerleştirilir. Varsa hiçbir **emitidl** özniteliği, kaynak kodu dosyasının IDL öznitelikleri oluşturulan .idl dosyasına çıkarılır.  
  
Birden çok olması mümkündür **emitidl** kaynak kodu dosyasının öznitelikleri. Varsa `[emitidl(false)];` bir dosyada bir sonraki olmadan karşılaştı `[emitidl(true)];`, hiçbir öznitelik oluşturulan .idl dosyasına işlenir sonra.  
  
Derleyici yeni bir dosya karşılaştığında **emitidl** örtük olarak ayarlandığında **doğru**.  
  
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
[Öznitelikleri örnekleri](http://msdn.microsoft.com/en-us/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)