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
ms.openlocfilehash: b7e7e287d68bac0fe69417fe21df27ed3231cce6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="eventsource"></a>event_source
Bir olay kaynağı oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ event_source(  
   type,  
   optimize=[speed | size],  
   decorate=[true | false]  
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `type`  
 Numaralandırması şu değerlerden biri:  
  
-   `native` Yönetilmeyen C/C++ için kod (yönetilmeyen sınıflar için varsayılan).  
  
-   `com` COM kod. Kullanmalısınız `coclass` zaman `type` = `com`. Bu değer aşağıdaki üstbilgi dosyaları dahil etme gerektirir:  
  
    ```  
    #define _ATL_ATTRIBUTES  
    #include <atlbase.h>  
    #include <atlcom.h>  
    ```  
  
 **optimize**  
 Zaman `type` olan **yerel**, belirtebilirsiniz **en iyi duruma getirme = boyutu**olduğunu depolama 4 bayt (en az) için tüm olayları bir sınıfta belirtmek için veya **en iyi duruma getirme hızı =** (4 olduğunu belirtmek için varsayılan) * depolama (olay sayısı) bayt.  
  
 **İşaretleme**  
 Zaman `type` olan **yerel**, belirleyebileceğiniz **tasarlamanız = false**, birleştirilmiş (.mrg) dosyasında genişletilmiş adı kapsayan sınıf adını içermemelidir belirtmek için. [/FX](../build/reference/fx-merge-injected-code.md) .mrg dosyaları oluşturmanıza olanak sağlar. **İşaretleme = false**, varsayılan değer, birleştirilmiş dosyanın tam nitelenmiş tür adları sonuçlanıyor.  
  
## <a name="remarks"></a>Açıklamalar  
 **Event_source** C++ özniteliği, sınıf veya yapı için bunu uygulandığı bir olay kaynağı olacağını belirtir.  
  
 **event_source** ile birlikte kullanılan [event_receiver](../windows/event-receiver.md) özniteliği ve [__event](../cpp/event.md) anahtar sözcüğü. Kullanım **event_receiver** Olay alıcıları oluşturmak için. Kullanım `__event` bu yöntemleri olayları olarak belirtmek için olay kaynağı içinde yöntemleri.  
  
> [!NOTE]
>  Şablonlu bir alan veya yapı, olay içeremez.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|**sınıf**, `struct`|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|**coclass'ı** zaman `type` = **com**|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici öznitelikleri](../windows/compiler-attributes.md)   
 [event_receiver](../windows/event-receiver.md)   
 [__Event](../cpp/event.md)   
 [__hook](../cpp/hook.md)   
 [__unhook](../cpp/unhook.md)   
 [Sınıf Öznitelikleri](../windows/class-attributes.md)   
