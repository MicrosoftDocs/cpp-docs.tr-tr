---
title: "uuid (C++ öznitelikleri) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.uuid
dev_langs: C++
helpviewer_keywords: uuid attribute
ms.assetid: 90562a94-5e28-451b-a4b0-cadda7f66efe
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ba35dc89ae2567a499d4623f0c74293d2dbdcca2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="uuid-c-attributes"></a>uuid (C++ Öznitelikleri)
Sınıfta veya arabirimde benzersiz Kimliğini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ uuid(  
   "uuid"  
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 *UUID*  
 128-bit, benzersiz tanımlayıcısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir arabirim ya da sınıf tanımını belirtme `uuid` C++ öznitelik sonra Visual C++ derleyicisi sağlayacaktır biri. Belirttiğinizde bir `uuid`, tırnak işaretleri eklemeniz gerekir.  
  
 Belirtmezseniz, `uuid`, derleyici bir makinede farklı öznitelik projelerinde arabirimleri veya aynı ada sahip sınıfları için aynı GUID oluşturur.  
  
 Kendi benzersiz kimlikler oluşturmak için Uuidgen.exe veya Guidgen.exe kullanabilirsiniz. (Bu araçlardan birini çalıştırmak için tıklatın **Başlat** tıklatıp **çalıştırmak** menüsünde. Ardından gerekli aracı adını girin.)  
  
 Ayrıca ATL kullanmayan bir proje ile kullanıldığında, belirtme `uuid` özniteliği aynıdır belirtme [UUID](../cpp/uuid-cpp.md) __declspec değiştiricisi. Alınacak `uuid` bir sınıfı, kullandığınız [__uuidof](../cpp/uuidof-operator.md)  
  
## <a name="example"></a>Örnek  
 Bkz: [bağlanabilirse](../windows/bindable.md) bir örnek kullanımı, örneğin `uuid`.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|**sınıf**, `struct`, `interface`, **UNION**,`enum`|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Arabirim öznitelikleri](../windows/interface-attributes.md)   
 [Sınıf öznitelikleri](../windows/class-attributes.md)   
 [TypeDef, Enum, Union ve Struct öznitelikleri](../windows/typedef-enum-union-and-struct-attributes.md)   
 [UUID](http://msdn.microsoft.com/library/windows/desktop/aa367302)   
