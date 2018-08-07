---
title: event_source | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.event_source
dev_langs:
- C++
helpviewer_keywords:
- event handling, attributes
- event logs, event source
- event sources, creating
- event_source attribute
- event sources
- event handling, creating event source
ms.assetid: 0983e36a-6127-4fbb-8a22-8dfec6564c16
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e44b5757ea7b9e469275688443ba7ed1e3810571
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39571395"
---
# <a name="eventsource"></a>event_source
Olay kaynağı oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[ event_source(  
   type,  
   optimize=[speed | size],  
   decorate=[true | false]  
) ]  
```  
  
### <a name="parameters"></a>Parametreler  
 *Türü*  
 Sabit listesi aşağıdaki değerlerden biri:  
  
-   `native` Yönetilmeyen C/C++ kodu için (yönetilmeyen sınıflar için varsayılan).  
  
-   `com` COM kodu için. Kullanmalısınız `coclass` olduğunda `type` = `com`. Bu değer, aşağıdaki üst bilgi dosyaları eklemenizi gerektirir:  
  
    ```  
    #define _ATL_ATTRIBUTES  
    #include <atlbase.h>  
    #include <atlcom.h>  
    ```  
  
 *optimize*  
 Zaman *türü* olduğu `native`, belirtebilirsiniz `optimize=size`olduğunu depolamanın 4 bayt (en az) için tüm olayları bir sınıfta belirtmek için veya `optimize=speed` (4 olduğunu göstermek için varsayılan) * (olay sayısı) depolama baytı.  
  
 *İşaretleme*  
 Zaman *türü* olduğu `native`, belirtebileceğiniz `decorate=false`, birleştirilmiş (.mrg) dosyasında genişletilmiş adının kapsayan sınıf adını içermemelidir belirtmek için. [/FX](../build/reference/fx-merge-injected-code.md) .mrg dosyaları oluşturmanıza olanak tanır. `decorate=false`, varsayılan değer, tam olarak nitelenmiş tür adlarını birleştirilmiş dosya sonuçlanıyor.  
  
## <a name="remarks"></a>Açıklamalar  
 **Event_source** C++ özniteliği, sınıf veya yapı, uygulandığı bir olay kaynağı olacağını belirtir.  
  
 **event_source** ile birlikte kullanılan [event_receiver](../windows/event-receiver.md) özniteliği ve [__event](../cpp/event.md) anahtar sözcüğü. Kullanım `event_receiver` Olay alıcıları oluşturmak için. Kullanım **__event** olaylar olarak söz konusu yöntemleri belirtmek için olay kaynağı içindeki yöntemlerde.  
  
> [!NOTE]
>  Şablonlu bir alan veya yapı, olay içeremez.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**İçin geçerlidir**|**sınıf**, **yapısı**|  
|**Tekrarlanabilir**|Hayır|  
|**Gerekli öznitelikleri**|**coclass'ı** olduğunda `type`=`com`|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Daha fazla bilgi için [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici öznitelikleri](../windows/compiler-attributes.md)   
 [event_receiver](../windows/event-receiver.md)   
 [__Event](../cpp/event.md)   
 [__hook](../cpp/hook.md)   
 [__unhook](../cpp/unhook.md)   
 [Sınıf Öznitelikleri](../windows/class-attributes.md)   