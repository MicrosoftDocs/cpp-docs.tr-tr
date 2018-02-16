---
title: "Özellikler (C + +/ CX) | Microsoft Docs"
ms.custom: 
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
ms.assetid: 64c7bc56-3191-4cd5-bdf4-476d07d285d5
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 446f2c4f18f68a4a52614397b697409d34b958de
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="properties-ccx"></a>Özellikler (C + +/ CX)
Windows çalışma zamanı türleri ortak veri özellikleri olarak kullanıma sunar. İstemci kodu ortak datamember gibi özelliği erişir. Dahili olarak, özellik bir get erişimcisine yöntemi, bir set erişimcisi yöntemi ya da her ikisini de içeren bir blok olarak uygulanır. Erişimci yöntemlerini kullanarak önce ek eylemler gerçekleştirebilirsiniz veya değer aldıktan sonra Örneğin, bir olay tetikleyin veya doğrulama denetimlerini gerçekleştiren.  
  
### <a name="remarks"></a>Açıklamalar  
 Özel bir değişkende bir özelliğin değerini içerdiği — olarak bilinen *yedekleme deposu*— özelliği aynı türde değil. Bir özellik yedekleme deposu için bir değer atayan bir set erişimcisi ve yedekleme deposu değerini alan bir get erişimcisine içerebilir. Her iki erişimciler sağlıyorsa, yalnızca bir set erişimcisi ve okuma/yazma (değiştirilebilir) sağlıyorsa yalnızca bir get erişimcisine, yalnızca yazma sağlarsa, salt okunur bir özelliktir.  
  
 A *Önemsiz* için derleyici otomatik olarak uygulayan erişimciler ve yedekleme deposu okuma/yazma özelliği bir özelliktir. Derleyicinin uygulamaya erişimi yok. Ancak, özel bir özelliği bildirme ve açıkça erişimciler ve yedekleme deposu bildirin. Erişimci içinde set erişimcisine girişi doğrulama, özellik değeri arasında bir değer hesaplama, bir veritabanına erişirken veya özelliği değiştiğinde bir olay tetikleme gibi gerektiren herhangi bir mantık gerçekleştirebilirsiniz.  
  
 C + zaman +/ CX ref sınıf örneği, kendi bellek sıfır-kurucusu çağrılmadan önce; başlatılır Bu nedenle tüm özellikler varsayılan değeri sıfır veya bildirimi noktasında nullptr atanır.  
  
### <a name="examples"></a>Örnekler  
 Aşağıdaki kod örneğinde, bildirme ve bir özellik erişim gösterilmektedir. İlk özelliği `Name`, olarak bilinen bir *Önemsiz* özelliği derleyici otomatik olarak oluşturduğundan bir `set` erişimci `get` erişimci ve yedekleme deposu.  
  
 İkinci özelliği `Doctor`, belirtir özelliği salt okunur olduğundan bir *özelliği bloğu* açıkça bildiren yalnızca bir `get` erişimcisi. Özellik blok bildirildiğinden yedekleme deposu açıkça bildirmeniz gerekir; diğer bir deyişle, özel dize ^ değişkeni `doctor_`. Genellikle, salt okunur bir özellik, yalnızca yedekleme deposu değerini döndürür. Sınıfının kendisi yalnızca yedekleme deposu değerini genellikle oluşturucuda ayarlayabilirsiniz.  
  
 Üçüncü özellik `Quantity`, her ikisi de bildiren bir özelliği bloğu bildirdiğinden okuma-yazma özelliği olan bir `set` erişimcisi ve `get` erişimcisi.  
  
 `set` Erişimci atanan değeri bir kullanıcı tarafından tanımlanan geçerlilik testi gerçekleştirir. Ve aksine C#, burada adı *değeri* yalnızca parametresinde tanımlayıcısıdır `set` erişimci; bir anahtar değil. Varsa *değeri* sıfırdan büyük değil Platform::InvalidArgumentException oluşur. Aksi takdirde, yedekleme depolamak, `quantity_`, atanan değeriyle güncelleştirilir.  
  
 Bir özellik üyesi listesinde başlatılamaz unutmayın. Elbette, yedekleme depolama değişkenleri bir üye listesinde başlatabilirsiniz.  
  
 [!code-cpp[cx_properties#01](../cppcx/codesnippet/CPP/cx_properties/class1.h#01)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tür sistemi](../cppcx/type-system-c-cx.md)   
 [Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)   
 [Ad alanları başvurusu](../cppcx/namespaces-reference-c-cx.md)