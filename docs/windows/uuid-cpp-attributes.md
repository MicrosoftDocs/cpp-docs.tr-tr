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
ms.openlocfilehash: 07258b2f7416b0747be81075f4c037a6be54e7a6
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39647079"
---
# <a name="uuid-c-attributes"></a>uuid (C++ Öznitelikleri)
Bir sınıf veya arabirim için benzersiz Kimliğini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[ uuid(  
   "uuid"  
) ]  
```  
  
### <a name="parameters"></a>Parametreler  
 *uuid*  
 128-bit, benzersiz tanımlayıcısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir arabirim veya sınıf tanımını belirtme **UUID** C++ özniteliği ve ardından Visual C++ derleyicisi sağlar; biri. Belirttiğinizde bir **UUID**, tırnak işaretleri eklemeniz gerekir.  
  
 Siz belirtmezseniz **UUID**, derleyici bir makinede farklı öznitelik projelerinde arabirimler veya aynı ada sahip sınıflar için aynı GUID oluşturur.  
  
 Uuidgen.exe veya Guidgen.exe kendi benzersiz kimlikler oluşturmak için kullanabilirsiniz. (Bu araçlardan birini çalıştırmak için tıklayın **Başlat** tıklatıp **çalıştırma** menüsünde. Ardından gerekli aracının adını girin.)  
  
 ATL ayrıca kullanmayan bir projede kullanılan belirttiğinizde **UUID** özniteliktir belirtmekle aynı [UUID](../cpp/uuid-cpp.md) **__declspec** değiştiricisi. Alınacak **UUID** bir sınıfı, kullandığınız [__uuidof](../cpp/uuidof-operator.md)  
  
## <a name="example"></a>Örnek  
 Bkz: [bağlanabilir](../windows/bindable.md) örnek kullanımını örneğin **UUID**.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**İçin geçerlidir**|**sınıf**, **yapı**, **arabirimi**, **birleşim**, **sabit listesi**|  
|**Tekrarlanabilir**|Hayır|  
|**Gerekli öznitelikleri**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Arabirim öznitelikleri](../windows/interface-attributes.md)   
 [Sınıf öznitelikleri](../windows/class-attributes.md)   
 [TypeDef, Enum, Union ve Struct öznitelikleri](../windows/typedef-enum-union-and-struct-attributes.md)   
 [uuid](http://msdn.microsoft.com/library/windows/desktop/aa367302)   