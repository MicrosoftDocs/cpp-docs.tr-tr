---
title: Özellikler (C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 64c7bc56-3191-4cd5-bdf4-476d07d285d5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f5cfe1bf4ae614bc892b4ea93d36fa44604029f1
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43764312"
---
# <a name="properties-ccx"></a>Özellikler (C + +/ CX)
Windows çalışma zamanı türleri genel veriler özellik olarak kullanıma sunar. İstemci kodu özellik genel datamember gibi erişir. Dahili olarak, özellik get erişimcisi yöntemi, bir set erişeni yöntemi veya her ikisini de içeren bir blok olarak uygulanır. Erişimci yöntemlerini kullanarak önce ek eylemler gerçekleştirebilirsiniz veya değer aldıktan sonra Örneğin, bir olay harekete veya doğrulama denetimleri gerçekleştirin.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir özelliğin değerini özel bir değişkende yer alan — olarak bilinen *yedekleme deposu*— özelliği olarak aynı türü. Bir özellik, yedekleme deposu için bir değer atayan bir set erişimcisi hem yedekleme deposu değerini alır. bir alma erişimcisi içerebilir. Özelliği, her iki erişimcisi sağlıyorsa, yalnızca bir set erişimcisine ve okuma/yazma (değiştirilebilir) sağlıyorsa yalnızca bir alma erişimcisi, salt yazılır sağlıyorsa salt okunur.  
  
 A *Önemsiz* için derleyicinin otomatik olarak uygulayan erişimciler ve yedekleme deposu bir okuma/yazma özelliği bir özelliktir. Derleyicinin uygulamasına erişiminiz yok. Ancak, özel bir özelliği bildirme ve yedekleme deposu ve erişimcileri açıkça bildirin. Erişimci içinde set erişimcisine girişi doğrulama, özellik değeri arasında bir değer hesaplamak, bir veritabanına erişme veya özelliği değiştiğinde bir olay tetikleme gibi gerektiren herhangi bir mantık gerçekleştirebilirsiniz.  
  
 C + olduğunda +/ CX başvuru sınıfı örneği, kendi bellek sıfır-kendi Oluşturucusu çağırılmadan önce; başlatılır Bu nedenle tüm özellikler varsayılan değer sıfır ya da bildirim noktasında nullptr olarak atanır.  
  
### <a name="examples"></a>Örnekler  
 Aşağıdaki kod örneği, bildirme ve bir özelliğe erişmek gösterilmektedir. İlk özellik `Name`, olarak da bilinen bir *Önemsiz* özelliği derleyici otomatik olarak oluşturduğundan bir `set` erişimci `get` erişimcisi ve bir yedekleme deposu.  
  
 İkinci özelliği `Doctor`, belirttiği için bir salt okunur özelliği olan bir *özelliği bloğu* açıkça bildiren yalnızca bir `get` erişimcisi. Özelliği bloğu bildirildiği için bir yedekleme deposu açıkça bildirmeniz gerekir; diğer bir deyişle, özel dize ^ değişken `doctor_`. Genellikle, salt okunur bir özellik, yalnızca yedekleme deposu değerini döndürür. Sınıfın kendisi yalnızca yedekleme deposu değerini genellikle oluşturucuda ayarlayabilirsiniz.  
  
 Üçüncü özellik `Quantity`, her ikisi de bildiren bir özelliği bloğu bildirdiğinden bir okuma-yazma özelliği olan bir `set` erişimci ve `get` erişimcisi.  
  
 `set` Erişimci atanan değer üzerinde bir kullanıcı tarafından tanımlanan geçerlilik test gerçekleştirir. Ve C#, adın buraya aksine *değer* parametresi için yalnızca tanımlayıcı `set` erişimci; bir anahtar değil. Varsa *değer* sıfırdan büyük değilse Platform::ınvalidargumentexception harekete geçirilir. Aksi takdirde, yedekleme depolama, `quantity_`, atanan değeriyle güncelleştirilir.  
  
 Üye listesinde bir özelliği başlatılamıyor unutmayın. Elbette, yedekleme deposu değişkenlerini bir üye listesinde başlatabilirsiniz.  
  
 [!code-cpp[cx_properties#01](../cppcx/codesnippet/CPP/cx_properties/class1.h#01)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tür sistemi](../cppcx/type-system-c-cx.md)   
 [Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)   
 [Ad alanları başvurusu](../cppcx/namespaces-reference-c-cx.md)