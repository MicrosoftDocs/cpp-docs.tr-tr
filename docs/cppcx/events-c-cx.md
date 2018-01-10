---
title: Olaylar (C + +/ CX) | Microsoft Docs
ms.custom: 
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31c8e08a-00ad-40f9-8f7e-124864aaad58
caps.latest.revision: "17"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: af74c81186591062214e2a8eb1695a2d177cfc04
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="events-ccx"></a>Olaylar (C + +/ CX)
Bir Windows türü bildirebilirsiniz (Yayımlama) çalışma zamanı olayları ve istemci kodu aynı bileşenin veya diğer bileşenleri abone olabilir, bu olaylarla adlı yöntemler ilişkilendirerek *olay işleyicileri* olay ile. Birden çok olay işleyicileri tek bir olayla ilişkili olabilir. Olay yayımlama nesnesini başlatır, çağrılacak tüm olay işleyicileri neden olur. Bu şekilde, yayımcı olayını ne olursa olsun özel eylem uygun olduğunda abone sınıfı gerçekleştirebilirsiniz. Bir olay olaya abone olmak için tüm olay işleyicileri içermelidir imza belirten bir temsilci türü vardır.  
  
## <a name="consuming-events-in-windows-components"></a>Windows bileşenleri olayları kullanma  
 Windows çalışma zamanı birçok bileşenlerinde olayları gösterir. Örneğin, bir LightSensor nesnesi algılayıcı yeni bir parlaklığı değer bildirdiğinde bir ReadingChanged olay gönderir. Programınıza LightSensor nesnesini kullandığınızda, ReadingChanged olay başlatıldığında çağrılacak bir yöntem tanımlayabilirsiniz. Yöntemi, bunu yapmak için istediğiniz yapabilirsiniz; yalnızca bir temsilci olay işleyicisi oluşturun ve bir olaya abone bkz hakkında daha fazla bilgi için temsilci imza imzası eşleşmelidir gereksinimdir [Temsilciler](../cppcx/delegates-c-cx.md).  
  
## <a name="creating-custom-events"></a>Özel olaylar oluşturma  
  
### <a name="declaration"></a>Bildirim  
 Ref sınıfı ya da bir arabirim olayda bildirin ve genel, dahili (ortak/özel) olabilir, genel korumalı, korumalı, özel korumalı veya özel erişilebilirlik. Bir olay bildirme, Dahili derleyici iki erişimci yöntemleri gösteren bir nesne oluşturur: ekleme ve kaldırma. Abone nesneleri olay işleyicileri kaydettiğinizde, olay nesnesi bunları bir koleksiyondaki depolar. Bir olay başlatıldığında olay nesnesi, listedeki tüm işleyiciler sırayla çağırır. Önemsiz olay — ister aşağıdaki örnekte bir — de olarak örtük bir örtük yedekleme deposu sahip `add` ve `remove` erişimci yöntemleri. Kendi erişimciler özel belirtebilirsiniz aynı şekilde belirtebilirsiniz `get` ve `set` bir özelliğe erişimciler.  Uygulayan sınıfa el ile önemsiz bir olay Olay abone listesinde dolaşmak olamaz.  
  
 Aşağıdaki örnek, bildirme ve bir olay tetikleyin gösterilmektedir. Olay bir temsilci türü var ve kullanarak bildirilmiş bildirimi "^" simgesi.  
  
 [!code-cpp[cx_events#01](../cppcx/codesnippet/CPP/cx_events/class1.h#01)]  
  
### <a name="usage"></a>Kullanım  
 Aşağıdaki örnek, bir abone sınıf nasıl kullandığını gösterir `+=` olaya abone ve olay başlatıldığında çağrılacak olay işleyicisi sağlamak için işleci. Sağlanan işlev Yayımcı tarafında tanımlanan temsilci imza eşleştiğini fark `EventTest` ad alanı.  
  
 [!code-cpp[cx_events#02](../cppcx/codesnippet/CPP/eventsupportinvs/eventclientclass.h#02)]  
  
> [!WARNING]
>  Genel olarak, döngüsel başvurulara önlemek için çok dikkatli almadıkça bir lambda yerine adlandırılmış bir işlev için olay işleyicisini kullanmak en iyisidir. Bir lambda güçlü başvuruya göre yakalar ve bir döngüsel başvuru oluşturur ancak isimli bir işlev "Bu" işaretçiyi zayıf başvuruya göre yakalar. Daha fazla bilgi için bkz: [zayıf başvurular ve kesme döngüleri (C + +/ CX)](../cppcx/weak-references-and-breaking-cycles-c-cx.md).  
  
### <a name="custom-add-and-remove-methods"></a>Özel yöntemler ekleyip  
 Dahili olarak, bir olay, bir ekleme yöntemi, Kaldır yöntemi ve artırma yöntemi vardır. İstemci kodu bir olaya abone olduğunda ekleme yöntemi olarak adlandırılır ve geçirilen temsilci olay çağırma listesine eklenir. Yayımlama sınıfı olayı çağırır, raise() yönteminin çağrılması başlamasına neden olur ve listedeki her temsilci sırayla çağrılır. Bir abonenin kendisini çağrılacak olayın Kaldır yöntemi neden temsilci listesinden kaldırabilirsiniz. Kodunuzda tanımlarsanız yok, bu yöntemleri varsayılan sürümlerini derleyici sağlar; Bunlar Önemsiz olayları olarak bilinir. Çoğu durumda, bir önemsiz gerekli olan tüm olayıdır.  
  
 Özel belirtebilirsiniz eklemek, kaldırmak ve raise yöntemlerinin bir olay için yanıt olarak eklenmesi veya aboneleri kaldırılması Özel mantık gerçekleştirmeniz gerekiyorsa. Örneğin, pahalı bir nesne varsa, bir istemci gerçekte olaya abone kadar olay raporlama için gerekli yalnızca, gevşek nesnesinin oluşturulmasını ertele.  
  
 Sonraki örnek özel ekleme gösterir eklemek, kaldırmak ve raise yöntemlerinin bir olay için:  
  
 [!code-cpp[cx_events#03](../cppcx/codesnippet/CPP/cx_events/class1.h#03)]  
  
## <a name="removing-an-event-handler-from-the-subscriber-side"></a>Olay işleyici abone taraftan kaldırma  
 Bazı nadir durumlarda, önceden abone bir olay için bir olay işleyicisi kaldırmak isteyebilirsiniz. Örneğin, başka bir olay işleyicisi ile değiştirmek isteyebilirsiniz veya tarafından tutulan bazı kaynaklar silmek isteyebilirsiniz. Bir işleyici kaldırmak için sunucudan döndürülen EventRegistrationToken depolamak `+=` işlemi. Daha sonra kullanabilirsiniz `-=` belirteç işlecinin olay işleyicisi kaldırmak için.  Ancak, hatta kaldırıldıktan sonra özgün işleyici hala çağırılabilir. Bu nedenle, olay işleyici kaldırmak istiyorsanız, bir üye bayrağı oluşturun ve olay kaldırılır ve ardından olay işleyicisi, bayrağı denetle ve hemen ayarlanmış olup olmadığını döndürür ayarlayın. Sonraki örnek temel düzeni gösterir.  
  
 [!code-cpp[cx_events#04](../cppcx/codesnippet/CPP/eventsupportinvs/eventclientclass.h#04)]  
  
### <a name="remarks"></a>Açıklamalar  
 Birden çok işleyici aynı olayla ilişkili olabilir. Olay kaynağı, iş parçacığı tüm olay işleyicilerini içine sıralı olarak çağırır. Olay alıcı olay işleyicisi yöntemi içinde engelliyorsa, bu olay için diğer olay işleyicilerini çağırma gelen olay kaynağı engeller.  
  
 Olay kaynağı Olay alıcıları olay işleyicileri çağırır sırası garanti edilmez ve çağrıdan diğerine farklılık gösterebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tür sistemi](../cppcx/type-system-c-cx.md)   
 [Temsilciler](../cppcx/delegates-c-cx.md)   
 [Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)   
 [Ad alanları başvurusu](../cppcx/namespaces-reference-c-cx.md)