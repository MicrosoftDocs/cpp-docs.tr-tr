---
title: uuid (C++ öznitelikleri) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.uuid
dev_langs:
- C++
helpviewer_keywords:
- uuid attribute
ms.assetid: 90562a94-5e28-451b-a4b0-cadda7f66efe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e56793855b278e0631c39ebfcdc51669a001a24b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891538"
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
 *uuid*  
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
|**Uygulandığı öğe:**|**sınıf**, `struct`, `interface`, **UNION**, `enum`|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Arabirim öznitelikleri](../windows/interface-attributes.md)   
 [Sınıf öznitelikleri](../windows/class-attributes.md)   
 [TypeDef, Enum, Union ve Struct öznitelikleri](../windows/typedef-enum-union-and-struct-attributes.md)   
 [uuid](http://msdn.microsoft.com/library/windows/desktop/aa367302)   
