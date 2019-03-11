---
title: Olaylar (C + +/ CX)
ms.date: 01/22/2017
ms.assetid: 31c8e08a-00ad-40f9-8f7e-124864aaad58
ms.openlocfilehash: 8e7e8616831e66a7f59ed849fc92ef2553aadb5b
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57745088"
---
# <a name="events-ccx"></a>Olaylar (C + +/ CX)

Bir Windows türü bildirebilirsiniz (Yayımlama) çalışma zamanı olayları ve istemci kodu aynı bileşenin veya diğer bileşenleri abone olabilir, bu olaylarla adlı yöntemler ilişkilendirerek *olay işleyicileri* olaylı. Birden çok olay işleyicileri, tek bir olay ile ilişkili olabilir. Yayımlama nesne olayı oluşturan, tüm olay işleyicileri çağrılmasına neden olur. Bu şekilde, yayımcı olayını ne olursa olsun bir özel eylem uygundur abone sınıfı gerçekleştirebilirsiniz. Bir olay olaya abone için tüm olay işleyicilerine sahip olması imza belirten bir temsilci türü vardır.

## <a name="consuming-events-in-windows-components"></a>Windows bileşenleri olayları kullanma

Windows çalışma zamanı'ndaki birçok bileşen olayları gösterir. Örneğin, bir LightSensor nesnesi algılayıcı yeni parlaklığı değeri bildirdiğinde bir ReadingChanged olayı tetikler. Programınızda LightSensor nesne kullandığınızda ReadingChanged olay harekete çağrılacak bir yöntem tanımlayabilirsiniz. Yöntem ne olursa olsun yapmak istediğiniz yapabilirler. imzası bir temsilci olay işleyicisi oluşturun ve bir olaya abone görmek hakkında daha fazla bilgi için temsilcisinin imzasıyla eşleşmelidir tek gereksinim olmasıdır [Temsilciler](../cppcx/delegates-c-cx.md).

## <a name="creating-custom-events"></a>Özel olaylar oluşturma

### <a name="declaration"></a>Bildirim

Başvuru sınıfı veya arabirim, bir olay bildirebilir ve genel, iç (ortak/özel) sahip olabilir, genel korumalı, korumalı, özel korumalı veya özel erişilebilirlik. Dahili olarak bir olay bildirdiğinizde, derleyici iki erişimci yöntemlerini gösteren bir nesne oluşturur: ekleyip kaldırabilirsiniz. Olay nesnesiyle abone nesneleri olay işleyicilerini kaydedin, bunları bir koleksiyonda depolar. Olay tetiklendiğinde olay nesnesi, listedeki tüm işleyiciler sırayla çağırır. Önemsiz bir olay — ister aşağıdaki örnekte bir tane — de örtülü olarak bir örtük yedekleme deposu sahip `add` ve `remove` erişimci metotlarını. Kendi erişimcileri özel belirttiğiniz yolla belirtebilirsiniz `get` ve `set` özellikte erişimcileri.  Uygulayan sınıfa önemsiz bir olay Olay abonesi listesinde el ile geçiş yapamazsınız.

Aşağıdaki örnek, bildirme ve bir olay harekete gösterilmektedir. Olay bir temsilci türüne sahip ve kullanılarak bildirilen bildirimi "^" simgesi.

[!code-cpp[cx_events#01](../cppcx/codesnippet/CPP/cx_events/class1.h#01)]

### <a name="usage"></a>Kullanım

Aşağıdaki örnek, bir abone sınıfını nasıl kullandığını gösterir. `+=` işleci olaya abone olur ve bir olay işleyicisi, olay başlatıldığında çağrılacak sağlar. Sağlanan işlev Yayımcı tarafında içinde tanımlanan metot temsilcisinin imzası eşleştiğine dikkat edin `EventTest` ad alanı.

[!code-cpp[cx_events#02](../cppcx/codesnippet/CPP/eventsupportinvs/eventclientclass.h#02)]

> [!WARNING]
> Genel olarak, döngüsel başvuru kaçınmak için dikkatli almadıkları sürece, bir lambda yerine adlandırılmış bir işlev için bir olay işleyicisi kullanmak en iyisidir. Bir lambda güçlü başvuruya göre yakalayan ve döngüsel bir başvuru oluşturur ancak bir adlandırılmış işlev "Bu" işaretçiyi zayıf başvuru tarafından yakalar. Daha fazla bilgi için [zayıf başvurular ve döngüleri kesme (C + +/ CX)](../cppcx/weak-references-and-breaking-cycles-c-cx.md).

### <a name="custom-add-and-remove-methods"></a>Özel yöntemler ekleyip

Dahili olarak, bir olay Ekle yöntemi, bir kaldırma yöntemi ve bir raise yöntemi vardır. İstemci kodu bir olaya abone olduğunda Ekle yöntemi çağrılır ve iletilen temsilci olay çağırma listesine eklenir. Yayımlama sınıfı olayı çağırır, raise() yöntemin çağrılması neden olur ve listedeki her bir temsilciye sırayla çağrılır. Abone kendisini çağrılacak olayın Kaldır yöntemi neden temsilci listeden kaldırabilirsiniz. Derleyici, kodunuzda tanımlamazsanız varsayılan sürümleri bu yöntemlerin sağlar; Bu Önemsiz olaylar olarak bilinir. Çoğu durumda, önemsiz bir olay gereken şey.

Özel belirtebilirsiniz eklemek, kaldırmak ve yanıt eklenmesi veya kaldırılmasını aboneleri için özel mantığı gerçekleştirmeniz gerekiyorsa, bir olay için yöntemleri Yükselt. Örneğin, pahalı bir nesne varsa, bir istemci, aslında olaya abone olur kadar olay raporlama için gerekli yalnızca, gevşek nesne oluşturma ertele.

Sonraki örnek, özel ekleme işlemi açıklanır eklemek, kaldırmak ve raise yöntemlerinin bir olay için:

[!code-cpp[cx_events#03](../cppcx/codesnippet/CPP/cx_events/class1.h#03)]

## <a name="removing-an-event-handler-from-the-subscriber-side"></a>Bir olay işleyicisi Abone tarafında kaldırılıyor

Bazı nadir durumlarda, daha önce abone olan bir olay için bir olay işleyicisi kaldırmak isteyebilirsiniz. Örneğin, başka bir olay işleyicisi ile değiştirmek isteyebilirsiniz veya tarafından tutulan bazı kaynaklar silmek isteyebilirsiniz. İşleyiciyi kaldırmak için öğesinden döndürülen EventRegistrationToken depolamak `+=` işlemi. Ardından `-=` belirteç işlecinin bir olay işleyicisi kaldırmak için.  Ancak, hatta kaldırıldıktan sonra özgün işleyici hala çağırılabilir. Bu nedenle, bir olay işleyicisi kaldırmak istiyorsanız, bir üye bayrağı oluşturmak ve olay kaldırılır ve ardından olay işleyicisi, bayrağı denetle ve hemen ayarlanmış olup olmadığını döndürür ayarlayın. Sonraki örnek, temel düzeni gösterir.

[!code-cpp[cx_events#04](../cppcx/codesnippet/CPP/eventsupportinvs/eventclientclass.h#04)]

### <a name="remarks"></a>Açıklamalar

Birden çok işleyicisi aynı olay ile ilişkili olabilir. Olay kaynağı, aynı iş parçacığındaki tüm olay işleyicilerindeki içine sıralı olarak çağırır. Bir olay alıcısının olay işleyicisi yöntemi içinde engelliyorsa, bu olay için diğer olay işleyicileri çağırma gelen olay kaynağı engeller.

Olay alıcıları olay işleyicileri, olay kaynağı çağırır sırasını garanti edilmez ve çağrıdan diğerine farklılık gösterebilir.

## <a name="see-also"></a>Ayrıca bkz.

[Tür Sistemi](../cppcx/type-system-c-cx.md)<br/>
[Temsilciler](../cppcx/delegates-c-cx.md)<br/>
[Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad alanları başvurusu](../cppcx/namespaces-reference-c-cx.md)
