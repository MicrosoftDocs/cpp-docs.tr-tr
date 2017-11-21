---
title: __hook | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: __hook_cpp
dev_langs: C++
helpviewer_keywords:
- __hook keyword [C++]
- event handlers [C++], connecting events to
ms.assetid: f4cabb10-d293-4c0e-a1d2-4745ef9cc22c
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 98a18a7e145a2b23b13e38bd07d5b29c5a397d6f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="hook"></a>__hook
Bir işleyici yöntemi bir olay ile ilişkilendirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      long __hook(  
   &SourceClass::EventMethod,  
   source,  
   &ReceiverClass::HandlerMethod  
   [, receiver = this]  
);  
long __hook(  
   interface,  
   source  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 **&***SourceClass* `::` *oluşur*  
 Olay işleyicisi yöntemi kanca olay yöntemi için bir işaretçi:  
  
-   Yerel C++ olayları: *SourceClass* olay kaynağı sınıftır ve *oluşur* etkinliğidir.  
  
-   COM olayları: *SourceClass* olay kaynağı arabirim ve *oluşur* yöntemlerinden biridir.  
  
-   Yönetilen olayları: *SourceClass* olay kaynağı sınıftır ve *oluşur* etkinliğidir.  
  
 `interface`  
 İçin sayfaya arabirim adı `receiver`, yalnızca, COM Olay alıcıları için *layout_dependent* parametresinin [event_receiver](../windows/event-receiver.md) özniteliği **true**.  
  
 *Kaynak*  
 Olay kaynağı örneği için bir işaretçi. Koduna bağlı olarak `type` belirtilen **event_receiver**, *kaynak* şunlardan biri olabilir:  
  
-   Yerel olay kaynak nesne işaretçisi.  
  
-   Bir **IUnknown**-işaretçisi (COM kaynak) bağlı.  
  
-   Yönetilen nesne işaretçisi (için yönetilen olayları).  
  
 **&***ReceiverClass* `::``HandlerMethod`  
 Bir olaya sayfaya için olay işleyicisi yöntemi için bir işaretçi. İşleyici yöntemi bir sınıf veya aynı bir başvuru olarak belirtilir; sınıf adı belirtmezseniz, `__hook` içinde çağırıldığı emin olmanız için sınıf varsayar.  
  
-   Yerel C++ olayları: *ReceiverClass* olay alıcı sınıftır ve `HandlerMethod` işleyicisi.  
  
-   COM olayları: *ReceiverClass* olay alıcı arabirim ve `HandlerMethod` kendi işleyicileri biridir.  
  
-   Yönetilen olayları: *ReceiverClass* olay alıcı sınıftır ve `HandlerMethod` işleyicisi.  
  
 `receiver`(isteğe bağlı)  
 Olay alıcı sınıfının bir örneği için bir işaretçi. Bir alıcı belirtmezseniz, alıcı sınıf veya yapı, varsayılandır `__hook` olarak adlandırılır.  
  
## <a name="usage"></a>Kullanım  
 Olay alıcı sınıfı dışında ana dahil olmak üzere, herhangi bir işlev kapsamdaki kullanımda olabilir.  
  
## <a name="remarks"></a>Açıklamalar  
 İç işlevini `__hook` veya bir olay yöntemi ile bir işleyici yöntemi kanca ilişkilendirmek için olay alıcı içinde. Belirtilen olay kaynağı başlatır, belirtilen işleyici sonra çağrılır. Tek bir olay için birkaç işleyicileri kanca ya da tek bir işleyici birkaç olaylarına bağlayın.  
  
 İki tür vardır `__hook`. Çoğu durumda, ilk (dört bağımsız değişkeni) form özellikle, COM Olay alıcıları için kullanabileceğiniz *layout_dependent* parametresinin [event_receiver](../windows/event-receiver.md) özniteliği **false** .  
  
 Bu durumlarda yöntemlerden birini bir olayda tetiklemeden önce bir arabirimdeki tüm yöntemler kanca gerekmez; Olay işleme yöntemi sayfaya gerekir. İkinci (iki bağımsız değişkeni) biçiminde kullanabilirsiniz `__hook` yalnızca, bir COM olay alıcısı için *layout_dependent***= true**.  
  
 `__hook`bir long değeri döndürür. Sıfır olmayan bir dönüş değeri (yönetilen olayları throw bir özel durum) bir hata oluştuğunu gösterir.  
  
 Derleyici bir olay varlığını denetler ve olay imzası temsilci imzayla kabul eder.  
  
 COM olayları dışında `__hook` ve `__unhook` dışında olay alıcısı çağrılabilir.  
  
 Kullanmaya alternatif `__hook` += işleci kullanmaktır.  
  
 Yeni sözdiziminde yönetilen olayları kodlama hakkında daha fazla bilgi için bkz: [olay](../windows/event-cpp-component-extensions.md).  
  
> [!NOTE]
>  Şablonlu bir alan veya yapı, olay içeremez.  
  
## <a name="example"></a>Örnek  
 Bkz: [olay işleme yerel C++'ta](../cpp/event-handling-in-native-cpp.md) ve [olay işleme COM içinde](../cpp/event-handling-in-com.md) örnekleri için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [Olay işleme](../cpp/event-handling.md)   
 [event_source](../windows/event-source.md)   
 [event_receiver](../windows/event-receiver.md)   
 [__unhook](../cpp/unhook.md)   
 [__raise](../cpp/raise.md)