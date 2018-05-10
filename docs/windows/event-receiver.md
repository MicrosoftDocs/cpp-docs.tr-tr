---
title: event_receiver | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.event_receiver
dev_langs:
- C++
helpviewer_keywords:
- event_receiver attribute
- event receivers
- events [C++], event receivers (sinks)
- event handling [C++], attributes
- event handling [C++], creating receiver
- event sinks, creating
- event sinks
ms.assetid: bf8fe770-3ea2-4128-b46b-166222ee4097
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 01ab5aeee7d706da7016cb1ea1f01ff7367de888
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="eventreceiver"></a>event_receiver
Bir olay alıcısı (havuz) oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ event_receiver(  
   type   
   [, layout_dependent=false]   
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 `type`  
 Numaralandırması şu değerlerden biri:  
  
-   `native` Yönetilmeyen C/C++ kodu için (varsayılan yerel sınıfları için).  
  
-   `com` COM kod. Bu değer aşağıdaki üstbilgi dosyaları dahil etme gerektirir:  
  
    ```  
    #define _ATL_ATTRIBUTES  
    #include <atlbase.h>  
    #include <atlcom.h>  
    ```  
  
 **layout_dependent**  
 Belirtin *layout_dependent* yalnızca `type` = **com**. *layout_dependent* bir Boolean:  
  
-   **doğru** alıcı olanlar için bunlar sayfaya olay kaynağı tam olarak eşleşmelidir olay temsilcileri imza anlamına gelir. Olay alıcı işleyici adları ilgili olay kaynağı arabiriminde belirtilen adları eşleşmelidir. Kullanmalısınız **coclass** zaman *layout_dependent* olan **doğru**. Belirtmek için biraz daha verimlidir **doğru**.  
  
-   **false** (varsayılan) anlamına arama kuralı ve depolama sınıfı (sanal, statik ve diğerleri) ya da işleyici adları olay kaynağı arabirimi yöntemi adları eşleşen gerek olay yöntemi ve işleyicileri; eşleşmesi gerekmez.  
  
## <a name="remarks"></a>Açıklamalar  
 **Event_receiver** C++ özniteliği, sınıf veya yapı için bunu uygulandığı Visual C++ birleştirilmiş olay modelini kullanarak bir olay alıcısı olacağını belirtir.  
  
 **event_receiver** ile kullanılan [event_source](../windows/event-source.md) özniteliği ve [__hook](../cpp/hook.md) ve [__unhook](../cpp/unhook.md) anahtar sözcükler. Kullanım **event_source** olay kaynakları oluşturmak için. Kullanım `__hook` bir olay kaynağı olayları ("kanca") olay alıcı yöntemlere ilişkilendirmek için bir olay alıcının yöntemleri içinde. Kullanım `__unhook` bunları ilişkilendirmesini kaldırmak.  
  
 *layout_dependent* COM Olay alıcıları için yalnızca belirtilen (`type`=**com**). İçin varsayılan *layout_dependent* olan **false**.  
  
> [!NOTE]
>  Şablonlu bir alan veya yapı, olay içeremez.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|**sınıf**, `struct`|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|**coclass'ı** zaman *layout_dependent*=**true**|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici öznitelikleri](../windows/compiler-attributes.md)   
 [event_source](../windows/event-source.md)   
 [__Event](../cpp/event.md)   
 [__hook](../cpp/hook.md)   
 [__unhook](../cpp/unhook.md)   
 [Sınıf Öznitelikleri](../windows/class-attributes.md)   
