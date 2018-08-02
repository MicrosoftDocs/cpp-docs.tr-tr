---
title: __unhook | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __unhook
- __unhook_cpp
dev_langs:
- C++
helpviewer_keywords:
- event handlers [C++], dissociating events
- __unhook keyword [C++]
ms.assetid: 953a14f3-5199-459d-81e5-fcf015a19878
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 020ae54cdaaddc2f05a8c3b6e285bc2fd0403ee8
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463720"
---
# <a name="unhook"></a>__unhook
Bir olay işleyicisi yöntemi dissociates.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp 
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
 **&** *SourceClass* `::` *oluşur*  
 Olay işleyicisi yöntemi'ni tutulabilir olay yöntemi için bir işaretçi:  
  
-   Yerel C++ olayları: *SourceClass* olay kaynak sınıfı ve *oluşur* etkinliğidir.  
  
-   COM olayları: *SourceClass* olay kaynağı arabirim ve *oluşur* yöntemlerinden biridir.  
  
-   Yönetilen olaylar: *SourceClass* olay kaynak sınıfı ve *oluşur* etkinliğidir.  
  
 *interface*  
 Gelen unhooked arabirim adı *alıcı*, yalnızca, COM Olay alıcıları için *layout_dependent* parametresinin [event_receiver](../windows/event-receiver.md) özniteliktir **true**.  
  
 *Kaynak*  
 Olay kaynağının bir örneği için bir işaretçi. Kod bağlı olarak `type` belirtilen `event_receiver`, *kaynak* aşağıdakilerden biri olabilir:  
  
-   Yerel olay kaynak nesne işaretçisi.  
  
-   Bir `IUnknown`-işaretçi (COM kaynak) bağlı.  
  
-   Bir yönetilen nesne işaretçisi (yönetilen olaylar).  
  
 **&** *ReceiverClass* `::` `HandlerMethod`  
 Bir olaydan unhooked olmasını olay işleyicisi yöntemi için bir işaretçi. İşleyici, bir sınıf ya da aynı başvuru yöntemi olarak belirtilir; sınıf adı belirtmezseniz, **__unhook** sınıfı, bunu çağrılır olmasını varsayar.  
  
-   Yerel C++ olayları: *ReceiverClass* olay alıcısı sınıfına olduğu ve `HandlerMethod` işleyicidir.  
  
-   COM olayları: *ReceiverClass* olay alıcısı arabirim ve `HandlerMethod` ona ait işleyiciyi biridir.  
  
-   Yönetilen olaylar: *ReceiverClass* olay alıcısı sınıfına olduğu ve `HandlerMethod` işleyicidir.  
  
 *Alıcı*(isteğe bağlı)  
 Olay alıcısı sınıfına örneğine bir işaretçi. Bir alıcı belirtmezseniz, alıcı sınıfın veya yapının, varsayılan değer **__unhook** çağrılır.  
  
## <a name="usage"></a>Kullanım  
 Ana olay alıcısı sınıfına dışında da dahil olmak üzere, herhangi bir işlev kapsamı kullanımda olabilir.  
  
## <a name="remarks"></a>Açıklamalar  
 İç işlevini **__unhook** ilişkisini kaldırın veya "olay yöntemi bir işleyici yöntemi tutulabilir" için olay alıcısı'nda.  
  
 Üç tür vardır **__unhook**. Çoğu durumda, ilk (dört bağımsız değişken) biçimini kullanabilirsiniz. İkinci (iki bağımsız) biçiminde kullanabileceğiniz **__unhook** yalnızca bir COM olay alıcısının için; bu, tüm olay arabirimi unhooks. Belirtilen kaynaktan tüm temsilciler tutulabilir için üçüncü (tek bağımsız değişkenli) formu kullanabilirsiniz.  
  
 Sıfır dışında bir dönüş değeri bir hata oluştuğunu gösterir (bir özel durum yönetilen olaylar oluşturur).  
  
 Eğer **__unhook** bir olay ve değil zaten kancalandı olay işleyicisi, hiçbir etkisi olmaz.  
  
 Derleme zamanında derleyici olay var ve parametre türü ile belirtilen işleyici denetimi yapar doğrular.  
  
 COM olayları hariç **__hook** ve **__unhook** olay alıcısı çağrılabilir.  
  
 Kullanmaya alternatif **__unhook** -= işleci kullanmaktır.  
  
 Yeni sözdiziminde yönetilen olaylar kodlama hakkında daha fazla bilgi için bkz: [olay](../windows/event-cpp-component-extensions.md).  
  
> [!NOTE]
>  Şablonlu bir alan veya yapı, olay içeremez.  
  
## <a name="example"></a>Örnek  
 Bkz: [olay işleme yerel C++'ta](../cpp/event-handling-in-native-cpp.md) ve [com'da olay işleme](../cpp/event-handling-in-com.md) örnekleri için.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [anahtar sözcükler](../cpp/keywords-cpp.md)   
 [event_source](../windows/event-source.md)   
 [event_receiver](../windows/event-receiver.md)   
 [__Event](../cpp/event.md)   
 [__hook](../cpp/hook.md)   
 [__raise](../cpp/raise.md)