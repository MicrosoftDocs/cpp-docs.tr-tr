---
title: __unhook | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __unhook
- __unhook_cpp
dev_langs: C++
helpviewer_keywords:
- event handlers [C++], dissociating events
- __unhook keyword [C++]
ms.assetid: 953a14f3-5199-459d-81e5-fcf015a19878
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1513391aedf9a08cd1ece971d79fd5f6913d406d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="unhook"></a>__unhook
Bir olay işleyicisi yönteminden dissociates.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      long  __unhook(  
   &SourceClass::EventMethod,  
   source,  
   &ReceiverClass::HandlerMethod  
   [, receiver = this]   
);  
long  __unhook(   
   interface,  
   source  
);  
long  __unhook(  
   source   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 **&***SourceClass* `::` *oluşur*  
 Olay işleyicisi yöntemi unhook olay yöntemi için bir işaretçi:  
  
-   Yerel C++ olayları: *SourceClass* olay kaynağı sınıftır ve *oluşur* etkinliğidir.  
  
-   COM olayları: *SourceClass* olay kaynağı arabirim ve *oluşur* yöntemlerinden biridir.  
  
-   Yönetilen olayları: *SourceClass* olay kaynağı sınıftır ve *oluşur* etkinliğidir.  
  
 `interface`  
 Gelen unhooked arabirim adı `receiver`, yalnızca, COM Olay alıcıları için *layout_dependent* parametresinin [event_receiver](../windows/event-receiver.md) özniteliği **true**.  
  
 *Kaynak*  
 Olay kaynağı örneği için bir işaretçi. Koduna bağlı olarak `type` belirtilen **event_receiver**, *kaynak* şunlardan biri olabilir:  
  
-   Yerel olay kaynak nesne işaretçisi.  
  
-   Bir **IUnknown**-işaretçisi (COM kaynak) bağlı.  
  
-   Yönetilen nesne işaretçisi (için yönetilen olayları).  
  
 **&***ReceiverClass* `::``HandlerMethod`  
 Bir olay unhooked olması için olay işleyicisi yöntemi için bir işaretçi. İşleyici yöntemi bir sınıf veya aynı bir başvuru olarak belirtilir; sınıf adı belirtmezseniz, `__unhook` içinde çağırıldığı emin olmanız için sınıf varsayar.  
  
-   Yerel C++ olayları: *ReceiverClass* olay alıcı sınıftır ve `HandlerMethod` işleyicisi.  
  
-   COM olayları: *ReceiverClass* olay alıcı arabirim ve `HandlerMethod` kendi işleyicileri biridir.  
  
-   Yönetilen olayları: *ReceiverClass* olay alıcı sınıftır ve `HandlerMethod` işleyicisi.  
  
 `receiver`(isteğe bağlı)  
 Olay alıcı sınıfının bir örneği için bir işaretçi. Bir alıcı belirtmezseniz, alıcı sınıf veya yapı, varsayılandır `__unhook` olarak adlandırılır.  
  
## <a name="usage"></a>Kullanım  
 Olay alıcı sınıfı dışında ana dahil olmak üzere, herhangi bir işlev kapsamdaki kullanımda olabilir.  
  
## <a name="remarks"></a>Açıklamalar  
 İç işlevini `__unhook` ilişkisini kaldırın veya "bir olay yöntemi işleyici yönteminden unhook" için olay alıcı içinde.  
  
 Üç tür vardır `__unhook`. Çoğu durumda, ilk (dört bağımsız değişkeni) form kullanabilirsiniz. İkinci (iki bağımsız değişkeni) biçiminde kullanabilirsiniz `__unhook` yalnızca bir COM için olay alıcı; bu tüm olay arabirimini unhooks. Belirtilen kaynaktan tüm temsilcileri unhook için üçüncü (tek bağımsız değişkenli) formu kullanın.  
  
 Sıfır olmayan bir dönüş değeri belirten bir hata oluştu (bir özel durum yönetilen olayları oluşturur).  
  
 Çağırırsanız `__unhook` bir olay ve değil zaten sayfaya olay işleyicisi üzerinde hiçbir etkisi olmaz.  
  
 Derleme zamanında derleyici olay var ve parametresi ile belirtilen işleyici tür denetlemesi mu olduğunu doğrular.  
  
 COM olayları dışında `__hook` ve `__unhook` dışında olay alıcısı çağrılabilir.  
  
 Kullanmaya alternatif `__unhook` -= işleci kullanmaktır.  
  
 Yeni sözdiziminde yönetilen olayları kodlama hakkında daha fazla bilgi için bkz: [olay](../windows/event-cpp-component-extensions.md).  
  
> [!NOTE]
>  Şablonlu bir alan veya yapı, olay içeremez.  
  
## <a name="example"></a>Örnek  
 Bkz: [olay işleme yerel C++'ta](../cpp/event-handling-in-native-cpp.md) ve [olay işleme COM içinde](../cpp/event-handling-in-com.md) örnekleri için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [event_source](../windows/event-source.md)   
 [event_receiver](../windows/event-receiver.md)   
 [__Event](../cpp/event.md)   
 [__hook](../cpp/hook.md)   
 [__raise](../cpp/raise.md)