---
title: Arabirimler (C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 11034314-d54a-426d-923b-5ab7a6b9f8ce
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6be3b207f6bd64685f7ec1d3f6d2271ec3b83f17
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="interfaces-ccx"></a>Arabirimler (C + +/ CX)
Ref sınıfı en çok bir somut temel sınıfı devralabilirsiniz karşın, herhangi bir sayıda arabirimi sınıflarını uygulayabilirsiniz. Arabirim sınıfı (veya arabirim yapı) kendisi devralır (gerektiren birden çok veya) arabirim sınıfları, kendi üye işlevleri aşırı yüklenebilir ve türü parametrelerine sahip olabilirsiniz.  
  
## <a name="characteristics"></a>Özellikler  
 Arabirim şu özelliklere sahiptir:  
  
-   Arabirim sınıfı (veya yapı) ad alanı içinde bildirilmelidir ve ortak veya özel erişilebilirlik sahip olabilir. Yalnızca ortak arabirimler için meta veri gösterilen.  
  
-   Arabirim üyeleri özellikleri, yöntemleri ve olayları içerebilir.  
  
-   Tüm arabirimi örtük olarak ortak ve sanal üyeleridir.  
  
-   Alanları ve statik üyeler izin verilmez.  
  
-   Yöntem parametreleri özellikleri olarak kullanılan veya değerler yalnızca Windows çalışma zamanı türleri olabilir döndüren türleri; Bu temel türleri ve enum sınıf türleri içerir.  
  
## <a name="declaration-and-usage"></a>Bildirim ve kullanımı  
 Aşağıdaki örnek, bir arabirim bildirmek gösterilmektedir. Arabirim sınıfta veya yapı türü olarak bildirilebilir dikkat edin.  
  
 [!code-cpp[cx_interfaces#01](../cppcx/codesnippet/CPP/interfacestest/class1.h#01)]  
  
 Bir arabirim için ref sınıfta veya ref yapı bildirir ve sanal yöntemleri ve özellikleri uygular. Arabirim ve ref sınıfın aynı yöntemi parametre adları bu örnekte gösterildiği gibi kullanmanız gerekir:  
  
 [!code-cpp[cx_interfaces#02](../cppcx/codesnippet/CPP/interfacestest/class1.h#02)]  
  
## <a name="interface-inheritance-hierarchies"></a>Devralma hiyerarşileri arabirimi  
 Arabirim, bir veya daha fazla arabirimlerinden devralabilirsiniz. Ancak ref sınıfta veya yapı, bir arabirim devralınan arabirim üyeleri bildirme değil. B arabirimi A arabirimden devralan ve ref sınıfı C B'den devralır, hem A ve b C uygulamalıdır Bu, sonraki örnekte gösterilir.  
  
 [!code-cpp[cx_interfaces#03](../cppcx/codesnippet/CPP/interfacestest/class1.h#03)]  
  
## <a name="implementing-interface-properties-and-events"></a>Arabirim Özellikleri ve olayları uygulama  
 Önceki örnekte gösterildiği gibi arabirimi özellikleri uygulamak için Önemsiz sanal özellikleri kullanabilirsiniz. Ayrıca, özel alıcılar ve ayarlayıcılar uygulayan sınıfa de sağlayabilir.  Hem alıcı hem de ayarlayıcı, ortak bir arabirim özelliği olması gerekir.  
  
 [!code-cpp[cx_interfaces#04](../cppcx/codesnippet/CPP/interfacestest/class1.h#04)]  
  
 Arabirim yalnızca get veya yalnızca kümesi özelliği bildirirse, uygulayan sınıfa açıkça, bir alıcı veya ayarlayıcı sağlamalıdır.  
  
 [!code-cpp[cx_interfaces#05](../cppcx/codesnippet/CPP/interfacestest/class1.h#05)]  
  
 Ayrıca özel uygulayabilirsiniz ekleyin ve olayları yöntemlerini uygulayan sınıfa kaldırın.  
  
## <a name="explicit-interface-implementation"></a>Açık arabirim uygulaması  
 Ref sınıfı birden çok arabirimlerini uygular ve bu arabirimleri yöntemleri adları sahip ve imzalar derleyiciye aynı olduğunda, bir sınıf yöntemi uygulama arabirim yöntemini açıkça belirtmek için aşağıdaki sözdizimini kullanın.  
  
 [!code-cpp[cx_interfaces#06](../cppcx/codesnippet/CPP/interfacestest/class1.h#06)]  
  
## <a name="generic-interfaces"></a>Genel arabirimler  
 C + +/ CX, `generic` anahtar sözcüğü bir Windows çalışma zamanı parametreli türü göstermek için kullanılır. Meta verilerde yayılan ve tür parametreleri destekleyen herhangi bir dilde yazılan kod tarafından kullanılabilecek bir parametreli türü. Windows çalışma zamanı bazı genel arabirimler tanımlar — Örneğin, [Windows::Foundation::Collections::IVector\<T >](Windows::Foundation::Collections::IVector)— ancak bunu kullanıcı tanımlı ortak genel arabirimler oluşturma C + desteklemiyor +/ CX. Ancak, özel genel arabirimler oluşturabilirsiniz.  
  
 Windows çalışma zamanı türleri genel bir arabirim yazmak için nasıl kullanılabileceğini aşağıda verilmiştir:  
  
-   Genel kullanıcı tanımlı `interface class` içinde bir bileşeni, Windows meta veri dosyasına yayılan izin verilmiyor; bu nedenle, ortak erişilebilirlik sahip olamaz ve diğer .winmd dosyalarında istemci kodu, uygulayamaz. Aynı bileşeninde genel olmayan ref sınıflar tarafından uygulanabilir. Bir ortak ref sınıfı özel üye olarak yazın genel bir arabirim olabilir.  
  
     Aşağıdaki kod parçacığını genel bildirmek gösterilmiştir `interface class` ve ardından özel ref sınıfında uygulamak ve bir ortak ref sınıfı özel üye olarak ref sınıfını kullanın.  
  
     [!code-cpp[cx_interfaces#07](../cppcx/codesnippet/CPP/interfacestest/class1.h#07)]  
  
-   Genel arabirim erişilebilirlik, üyeler, yöneten standart arabirimi kurallara uymalıdır *gerektirir* ilişkileri, temel sınıflar ve benzeri.  
  
-   Genel arabirim tarafından öncesinde bir veya daha fazla genel tür parametreleri sürebilir `typename` veya `class`. Olmayan tür parametreleri desteklenmez.  
  
-   Tür parametresi herhangi bir Windows çalışma zamanı türü olabilir. Diğer bir deyişle, tür parametresi bir başvuru türü, bir değer türü, bir arabirim sınıfı, bir temsilci, temel türü veya ortak enum sınıfı olabilir.  
  
-   A *genel arabirimi kapatılmış* genel arabirimden devralan ve tüm tür parametreleri için somut tür bağımsız değişkenleri belirten bir arabirimdir. Bu, bir genel olmayan özel kullanıcı arabirimi kullanılabilir herhangi bir yerde kullanılabilir.  
  
-   Bir *genel arabirim açmak* için somut bir türde henüz sağlanır bir veya daha fazla tür parametresine sahip bir arabirimdir. Bu, bir tür, başka bir genel arabirim bir tür bağımsız değişkeni olarak da dahil olmak üzere kullanılabilir herhangi bir yerde kullanılabilir.  
  
-   Yalnızca tüm arabirim, bireysel yöntemleri Parametreleştirme.  
  
-   Tür parametreleri kısıtlaması olamaz.  
  
-   Kapalı bir genel arabirim örtük olarak oluşturulmuş bir UUID sahiptir. Bir kullanıcı UUID belirtemezsiniz.  
  
-   Arabiriminde, herhangi bir başvuru geçerli arabirimi — bir yöntem parametre değeri veya özelliği Döndür — geçerli örneklemesi başvurmak için kabul edilir. Örneğin, *IMyIntf* anlamına gelir *IMyIntf\<T >*.  
  
-   Yöntemi parametresinin türü bir tür parametresi olduğunda, bu parametre veya değişken bildirimi herhangi bir işaretçi, yerel başvurusu veya tanıtıcı bildirimleri olmadan türü parametrenin adını kullanır. Diğer bir deyişle, hiçbir zaman yazdığınız "T ^".  
  
-   Şablonlu ref sınıfları özel olması gerekir. Genel arabirimler uygulayabilirsiniz ve şablon parametresi geçirebilirsiniz *T* genel bağımsız değişken için *T*. Her örneklemesi şablonlu ref sınıfının kendisini ref sınıfıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tür sistemi](../cppcx/type-system-c-cx.md)   
 [Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)   
 [Ad alanları başvurusu](../cppcx/namespaces-reference-c-cx.md)