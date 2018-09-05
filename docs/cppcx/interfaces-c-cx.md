---
title: Arabirimler (C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 11034314-d54a-426d-923b-5ab7a6b9f8ce
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d8ed06b84ec53cddac2d76488f7d1540a92c1d52
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43764448"
---
# <a name="interfaces-ccx"></a>Arabirimler (C + +/ CX)
Başvuru sınıfı en fazla bir somut taban sınıfından devralabilir olsa da, herhangi bir sayıda arabirim sınıflarından aşımınızı uygulayabilirsiniz. Arabirim sınıfı (veya arabirimi struct) kendisi devralır (gerektiren birden çok veya) arabirim sınıfları, üye işlevleri aşırı yüklenebilir ve Tür parametrelerine sahip olabilir.  
  
## <a name="characteristics"></a>Özellikler  
 Bir arabirim şu özelliklere sahiptir:  
  
-   Bir arabirim sınıfı (ya da yapı) ad alanı içinde bildirilmelidir ve erişilebilirlik genel veya özel olabilir. Yalnızca ortak arabirimler için meta veriler gönderilir.  
  
-   Bir arabirim üyelerinin, özellikler, yöntemler ve olaylar içerebilir.  
  
-   Tüm arabirim üyeleri, örtük olarak ortak ve sanal.  
  
-   Alanları ve statik üyeler izin verilmez.  
  
-   Özellikler, yöntem parametreleri olarak kullanılan veya değerleri yalnızca Windows çalışma zamanı türleri olabilir dönüş türleri; Bu, temel türler ve sabit listesi sınıfı türleri içerir.  
  
## <a name="declaration-and-usage"></a>Bildirim ve kullanım  
 Aşağıdaki örnek, bir arabirim tanımlamak gösterilmektedir. Bir arabirim bir sınıf veya yapı türü olarak bildirilebilir dikkat edin.  
  
 [!code-cpp[cx_interfaces#01](../cppcx/codesnippet/CPP/interfacestest/class1.h#01)]  
  
 Bir arabirim uygulamak için bir başvuru sınıfının veya ref struct bildirir ve sanal yöntemleri ve özellikleri uygular. Arabirim ve uygulama başvuru sınıfı aynı yöntem parametre adları, bu örnekte gösterildiği gibi kullanmanız gerekir:  
  
 [!code-cpp[cx_interfaces#02](../cppcx/codesnippet/CPP/interfacestest/class1.h#02)]  
  
## <a name="interface-inheritance-hierarchies"></a>Devralma hiyerarşilerini arabirimi  
 Bir arabirim bir veya daha fazla ara birimden devralınabilir. Ancak, bir başvuru sınıfının veya yapı aksine, bir arabirim devralınan üyesi bildirmek değil. B arabirimi bir arabirimden devralan ve başvuru sınıfı C B'den devralır, hem A ve b C uygulamalıdır Bu bir sonraki örnekte gösterilir.  
  
 [!code-cpp[cx_interfaces#03](../cppcx/codesnippet/CPP/interfacestest/class1.h#03)]  
  
## <a name="implementing-interface-properties-and-events"></a>Arabirim Özellikleri ve olayları uygulama  
 Önceki örnekte gösterildiği gibi Önemsiz sanal özellikleri arabirimi özellikleri uygulamak için kullanabilirsiniz. Özel alıcılar ve ayarlayıcılar içinde uygulayan sınıfa de sağlayabilirsiniz.  Hem alıcı hem de ayarlayıcı arabirim özelliği genel olmalıdır.  
  
 [!code-cpp[cx_interfaces#04](../cppcx/codesnippet/CPP/interfacestest/class1.h#04)]  
  
 Bir arabirim yalnızca get veya set-yalnızca bir özelliği bildirir, uygulayan sınıfa açıkça, alıcı veya ayarlayıcı sağlamalıdır.  
  
 [!code-cpp[cx_interfaces#05](../cppcx/codesnippet/CPP/interfacestest/class1.h#05)]  
  
 Ayrıca özel uygulayabilirsiniz olayları yöntemlerini uygulayan sınıfı ekleyip.  
  
## <a name="explicit-interface-implementation"></a>Açık arabirim uygulaması  
 Bir başvuru sınıfının birden çok arabirimi uygulayan ve o arabirimlerin adları yöntem sahiptir ve derleyiciye imzaları aynıdır, bir sınıf yöntemi uygulama arabirim yöntemini açıkça belirtmek için aşağıdaki sözdizimini kullanın.  
  
 [!code-cpp[cx_interfaces#06](../cppcx/codesnippet/CPP/interfacestest/class1.h#06)]  
  
## <a name="generic-interfaces"></a>Genel arabirimler  
 C + +/ CX, `generic` anahtar sözcüğü, bir Windows parametreli çalışma zamanı türü göstermek için kullanılır. Bir parametreli tür meta verilerinde yayılır ve tür parametreleri destekleyen herhangi bir dilde yazılmış kod tarafından tüketilebilir. Windows çalışma zamanı bazı genel arabirimler tanımlar — Örneğin, [Windows::Foundation::Collections::IVector\<T >](Windows::Foundation::Collections::IVector)— ancak bunu kullanıcı tanımlı genel genel arabirimler oluşturma C + desteklemiyor +/ CX. Ancak, özel genel arabirimleri oluşturabilirsiniz.  
  
 Windows çalışma zamanı türleri bir genel arabirim yazmak için nasıl kullanılabileceğini aşağıda verilmiştir:  
  
-   Genel kullanıcı tanımlı `interface class` içinde bir bileşen kendi Windows meta veri dosyasına yayılan izin verilmiyor; bu nedenle, ortak erişilebilirlik sahip olamaz ve diğer .winmd dosyalarında istemci kodu, uygulayamaz. Genel olmayan başvuru sınıfları aynı bileşende tarafından uygulanabilir. Genel başvuru sınıfı türü özel üye olarak genel bir arabirim olabilir.  
  
     Aşağıdaki kod parçacığı, genel bildirmek gösterilmektedir `interface class` özel başvuru sınıfında uygulamak ve ortak başvuru sınıfı özel üye olarak başvuru sınıfı kullanın.  
  
     [!code-cpp[cx_interfaces#07](../cppcx/codesnippet/CPP/interfacestest/class1.h#07)]  
  
-   Genel arabirimi erişilebilirliği, üye, yöneten standart arabirimi kurallara uymalıdır *gerektirir* ilişkileri, temel sınıflar ve benzeri.  
  
-   Genel bir arabirim tarafından öncesinde bir veya daha fazla genel tür parametre alabilir `typename` veya `class`. Türü olmayan parametreler desteklenmez.  
  
-   Bir tür parametresi, herhangi bir Windows çalışma zamanı türü olabilir. Diğer bir deyişle, tür parametresi, bir başvuru türü, bir değer türü, arabirim sınıfı, bir temsilci, bir temel türü veya genel sabit listesi sınıfı olabilir.  
  
-   A *genel arabirimi kapatılmış* genel bir arabirimden devralan ve somut tür bağımsız değişkenleri için tüm tür parametreleri belirtir bir arabirimdir. Bu, genel olmayan bir özel arabirim kullanılabilir her yerde kullanılabilir.  
  
-   Bir *genel arabirimini açın* için hangi somut bir türde henüz sağlanan bir veya daha fazla tür parametresine sahip bir arayüzdür. Bu, bir tür, başka bir genel arabiriminin tür bağımsız değişkeni da dahil olmak üzere kullanılabileceğini her yerde kullanılabilir.  
  
-   Yalnızca bir arabirimin tamamı, bireysel yöntemleri parametreleştirebilirsiniz.  
  
-   Tür parametreleri kısıtlı olabilir.  
  
-   Kapalı genel bir arabirim bir örtük olarak oluşturulan UUID sahiptir. Bir kullanıcı UUID belirtemezsiniz.  
  
-   Arabiriminde herhangi başvurusu geçerli arabirimi — değeri veya özelliği bir yöntem parametresinde döndürür; geçerli örneklemesine başvurmak için kabul edilir. Örneğin, *IMyIntf* anlamına gelir *IMyIntf\<T >*.  
  
-   Bir yöntem parametresi türü bir tür parametresi, herhangi bir işaretçi, yerel başvuru veya tanıtıcı Bildirimciler olmadan tür parametre adı, parametre veya değişken bildirimini kullanır. Diğer bir deyişle, hiçbir zaman yazma "T ^".  
  
-   Şablonlu başvuru sınıfları özel olması gerekir. Genel arabirimler uygulayabilirsiniz ve şablon parametresi geçirebilirsiniz *T* genel bağımsız değişkene *T*. Şablonlu başvuru sınıfı her örneğinin kendisine bir başvuru sınıftır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tür sistemi](../cppcx/type-system-c-cx.md)   
 [Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)   
 [Ad alanları başvurusu](../cppcx/namespaces-reference-c-cx.md)