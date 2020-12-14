---
description: 'Daha fazla bilgi edinin: Özellikler (C++/CX)'
title: Özellikler (C++/CX)
ms.date: 01/22/2017
ms.assetid: 64c7bc56-3191-4cd5-bdf4-476d07d285d5
ms.openlocfilehash: 5c56dabb080404b074408f60b6c06535558c1d82
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239720"
---
# <a name="properties-ccx"></a>Özellikler (C++/CX)

Windows Çalışma Zamanı türler, genel verileri özellikler olarak kullanıma sunar. İstemci kodu, özelliğe ortak bir DataMember gibi erişir. Dahili olarak, özelliği get erişimcisi yöntemi, bir set erişimcisi yöntemi veya her ikisini de içeren bir blok olarak uygulanır. Erişimci yöntemlerini kullanarak, değeri almadan önce veya sonra ek eylemler gerçekleştirebilirsiniz, örneğin, bir olayı tetikleyerek veya doğrulama denetimleri gerçekleştirebilirsiniz.

### <a name="remarks"></a>Açıklamalar

Bir özelliğin değeri, özellik ile aynı türde olan bir özel değişkende (örneğin, *yedekleme deposu* olarak bilinir) bulunur. Bir özellik, yedekleme deposuna bir değer atayan bir set erişimcisi ve yedekleme deposunun değerini alan bir get erişimcisi içerebilir. Özelliği yalnızca bir get erişimcisi sağlıyorsa, salt yazılır, yalnızca bir küme erişimcisi sağlıyorsa, salt yazılır ve her iki erişimci de sağlıyorsa okuma/yazma (değiştirilebilir) olur.

*Önemsiz* özellik, derleyicinin erişimcileri ve yedekleme deposunu otomatik olarak uyguladığı bir okuma/yazma özelliğidir. Derleyicinin uygulamasına erişiminiz yok. Ancak, özel bir özellik bildirebilir ve kendi erişimcilerini ve yedekleme deposunu açıkça bildirebilirsiniz. Bir erişimci içinde, küme erişimcisine girişi doğrulamak, özellik değerindeki bir değeri hesaplamak, bir veritabanına erişmek veya özellik değiştiğinde bir olayı tetiketmek gibi, ihtiyacınız olan herhangi bir mantığı gerçekleştirebilirsiniz.

Bir C++/CX başvuru sınıfı örneği oluşturulduğunda, Oluşturucusu çağrılmadan önce belleği sıfır olarak başlatılır; Bu nedenle, tüm özelliklere bildirim noktasında varsayılan sıfır veya nullptr değeri atanır.

### <a name="examples"></a>Örnekler

Aşağıdaki kod örneği, bir özelliğin nasıl bildirilemeyeceğini ve erişebileceğini gösterir. `Name`Derleyici otomatik  olarak bir `set` erişimci, `get` erişimci ve bir yedekleme deposu oluşturduğundan, ilk özelliği önemsiz özellik olarak bilinir.

İkinci özelliği, `Doctor` yalnızca bir erişimciyi bildiren bir *özellik bloğunu* belirttiğinden, salt okunurdur `get` . Özellik bloğu bildirildiği için, açıkça bir yedekleme deposu bildirmeniz gerekir; Yani, özel dize ^ Variable, `doctor_` . Genellikle, salt okunurdur bir özellik yalnızca yedekleme deposunun değerini döndürür. Yalnızca sınıfın kendisi, genellikle oluşturucuda, yedekleme deposunun değerini ayarlayabilir.

Üçüncü özelliği, `Quantity` hem erişimci hem de erişimci bildiren bir özellik bloğu bildirdiğinden bir okuma-yazma özelliğidir `set` `get` .

`set`Erişimci atanan değer üzerinde Kullanıcı tanımlı bir geçerlilik testi gerçekleştirir. Ve C# ' nin aksine, ad *değeri* yalnızca `set` erişimcinin parametresinin tanımlayıcısıdır; bir anahtar sözcük değildir. *Değer* sıfırdan büyük değilse Platform:: InvalidArgumentException atılır. Aksi halde, yedekleme deposu, `quantity_` atanan değerle güncelleştirilir.

Bir özelliğin üye listesinde başlatılamaz olduğunu unutmayın. Bir üye listesinde mağaza değişkenlerini yedeklemeye yönelik bir kurs başlatabilirsiniz.

[!code-cpp[cx_properties#01](../cppcx/codesnippet/CPP/cx_properties/class1.h#01)]

## <a name="see-also"></a>Ayrıca bkz.

[Tür sistemi](../cppcx/type-system-c-cx.md)<br/>
[C++/CX dil başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad alanı başvurusu](../cppcx/namespaces-reference-c-cx.md)
