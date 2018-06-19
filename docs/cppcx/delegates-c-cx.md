---
title: Temsilciler (C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 3175bf1c-86d8-4eda-8d8f-c5b6753d8e38
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9936280d25933afb787d883139725b5a7044db6e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33092394"
---
# <a name="delegates-ccx"></a>Temsilciler (C + +/ CX)
`delegate` Anahtar sözcüğü bir işlev nesnesi standart C++'ta Windows çalışma zamanı denk bir başvuru türü bildirmek için kullanılır. Bir işlev imzasına benzer bir temsilci bildirimi; sarmalanmış işlev olmalıdır parametre türleri ve dönüş türünü belirtir. Bir kullanıcı tarafından tanımlanan temsilci bildirimi şudur:  
  
```cpp  
     public delegate void PrimeFoundHandler(int result);  
```  
  
 Temsilciler en yaygın olaylar ile birlikte kullanılır. Bir olay bir temsilci türü çok bir sınıf bir arabirim türü olabilir aynı şekilde vardır. Temsilci olay işleyicileri çok karşılayan bir sözleşme temsil eder. Önceden tanımlanmış temsilci türü olan bir olay sınıfı üyesi şöyledir:  
  
```cpp  
event PrimeFoundHandler^ primeFoundEvent;  
```  
  
 Açığa çıkarılması temsilciler Windows çalışma zamanı uygulama ikili arabirimi istemcilere bildirirken kullanmak [Windows::Foundation::TypedEventHandler\<TSender, TResult >](http://msdn.microsoft.com/library/windows/apps/br225997.aspx). Bu temsilci Javascript istemciler tarafından tüketilen etkinleştirmek proxy ve saplama ikili dosyalarını önceden tanımlanmış.  
  
## <a name="consuming-delegates"></a>Temsilcileri kullanma  
 Bir evrensel Windows Platform uygulaması oluşturduğunuzda, genellikle bir Windows çalışma zamanı sınıf gösteren bir olay türü olarak bir temsilci ile çalışır. Bir olaya abone olmak için bir işlev belirterek kendi temsilci türünün bir örneğini oluşturun — veya lambda — temsilci imza eşleşir. Ardından `+=` temsilci nesne sınıfında olay üyesine geçirmek için işleci. Bu olaya abone olma olarak bilinir. Sınıf örneği "olay başlatıldığında" nesnenizin veya diğer nesneleri tarafından eklenen diğer işleyicilerin yanı sıra, işlev çağrılır.  
  
> [!TIP]
>  Olay işleyici oluşturduğunuzda, visual Studio sizin için çok fazla iş yapar. Örneğin, olay işleyici XAML biçimlendirme belirtirseniz, araç ipucu görünür. Araç İpucu seçerseniz, Visual Studio, otomatik olarak olay işleyicisi yöntemi oluşturur ve olay yayımlama sınıfı üzerinde ile ilişkilendirir.  
  
 Aşağıdaki örnek temel düzeni gösterir. `Windows::Foundation::TypedEventHandler` Temsilci türüdür. İşleyici işlevi, adlandırılmış işlevi kullanılarak oluşturulur.  
  
 App.h içinde:  
  
 [!code-cpp[cx_delegates#120](../cppcx/codesnippet/CPP/delegatesevents/class1.h#120)]  
  
 App.cpp içinde:  
  
 [!code-cpp[cx_delegates#121](../cppcx/codesnippet/CPP/delegatesevents/class1.cpp#121)]  
  
> [!WARNING]
>  Genel olarak, bir olay işleyicisi için döngüsel başvurulara önlemek için çok dikkatli almadıkça isimli bir işlev yerine bir lambda kullanmak en iyisidir. İsimli bir işlev "Bu" işaretçiyi zayıf başvuruya göre yakalar, ancak bir lambda güçlü başvuruya göre yakalar ve bir döngüsel başvuru oluşturur. Daha fazla bilgi için bkz: [zayıf başvurular ve kesme döngüleri](../cppcx/weak-references-and-breaking-cycles-c-cx.md).  
  
 Kurala göre Windows çalışma zamanı tarafından tanımlanan olay işleyicisi temsilci adlarının biçimi şöyledir: * EventHandler — Örneğin, RoutedEventHandler, SizeChangedEventHandler veya SuspendingEventHandler. Ayrıca, kural tarafından olay işleyici temsilcileri iki parametreye sahiptir ve void döndürür. Türünde ilk parametre türü parametrelerine sahip olmayan bir temsilci, [Platform::Object ^](../cppcx/platform-object-class.md); olay harekete nesne gönderen bir başvuru içerir. Olay işleyicisi yönteminde bağımsız değişken kullanmadan önce geri özgün türe sahip. Tür parametreleri olan bir olay işleyici temsilcisi, ilk tür parametresi gönderen türünü belirtir ve ikinci parametre olayla ilgili bilgileri tutan bir ref sınıf için bir tanıtıcı olduğundan. Kurala göre o sınıfın adlı \*EventArgs. Örneğin, RoutedEventHandler RoutedEventArgs türünde ikinci bir parametresi temsilcinin ^, ve DragEventHander DragEventArgs türünde ikinci bir parametresi ^.  
  
 Kurala göre zaman uyumsuz bir işlem tamamlandığında yürütülen kodu sarmalamak temsilciler adlı * CompletedHandler. Bu temsilci sınıfındaki özellikleri olayları olarak değil olarak tanımlanır. Bu nedenle, kullanmadığınız `+=` ; abone olursanız işleci yalnızca bir temsilci nesnesi özelliğine atayın.  
  
> [!TIP]
>  C++ IntelliSense tam temsilci imza göstermez; Bu nedenle, onu EventArgs parametre türünü belirlemenize yardımcı değil. Türü bulmak için gidebilirsiniz **Nesne Tarayıcısı** ve bakmak `Invoke` temsilci yöntemi.  
  
## <a name="creating-custom-delegates"></a>Özel temsilci oluşturma  
 Olay işleyicileri tanımlamak veya özel işlevsellik, Windows çalışma zamanı bileşenine geçmek olanak sağlamak üzere kendi temsilciler tanımlayabilirsiniz. Diğer Windows çalışma zamanı türü gibi ortak bir temsilci olarak genel bildirilemez.  
  
### <a name="declaration"></a>Bildirim  
 Bir temsilci bildirimi işlev bildirimi benzer temsilci türüdür. Genellikle, bir sınıf bildirimi temsilci bildiriminde ayrıca geçirebilmenize rağmen ad alanı kapsamında bir temsilci bildirin. Aşağıdaki temsilci gereken herhangi bir işlev yalıtan bir `ContactInfo^` giriş ve döndürür olarak bir `Platform::String^`.  
  
 [!code-cpp[cx_delegates#111](../cppcx/codesnippet/CPP/delegatesevents/class1.h#111)]  
  
 Bir temsilci türü belirtmesi sonra bu tür ya da bu tür nesneleri parametre olarak geçirmesine yöntemleri sınıf üyeleri bildirebilirsiniz. Ayrıca bir yöntem veya işlevi bir temsilci türü geri dönebilirsiniz. Aşağıdaki örnekte, `ToCustomString` yöntemi temsilci giriş parametresi olarak alır. Bazı veya tüm ortak özelliklerinin bir dize oluşturur özel bir işlev sağlamak istemci kodu yöntemi etkinleştirir bir `ContactInfo` nesnesi.  
  
 [!code-cpp[Cx_delegates#112](../cppcx/codesnippet/CPP/delegatesevents/class1.h#112)]  
  
> [!NOTE]
>  Kullandığınız "^" sembol temsilci türüne başvurduğunuzda türü tüm Windows çalışma zamanı ile yalnızca başvuru olarak.  
  
 Bir olay bildirimi her zaman bir temsilci türü vardır. Bu örnek, tipik bir temsilci gösterir Windows çalışma zamanı tür imzası:  
  
 [!code-cpp[cx_delegates#122](../cppcx/codesnippet/CPP/delegatesevents/class1.h#122)]  
  
 `Click` Olayında `Windows:: UI::Xaml::Controls::Primitives::ButtonBase` sınıftır türü `RoutedEventHandler`. Daha fazla bilgi için bkz: [olayları](../cppcx/events-c-cx.md).  
  
 İstemci kodu ilk kullanarak temsilci örneği oluşturur `ref new` ve temsilci imza ile uyumludur ve özel davranışını tanımlayan bir lambda sağlama.  
  
 [!code-cpp[Cx_delegates#113](../cppcx/codesnippet/CPP/delegatesevents/class1.cpp#113)]  
  
 Üye işlevini çağırır ve temsilci geçirir. Varsayımında `ci` olan bir `ContactInfo^` örneği ve `textBlock` bir XAML `TextBlock^`.  
  
 [!code-cpp[Cx_delegates#114](../cppcx/codesnippet/CPP/delegatesevents/class1.cpp#114)]  
  
 Sonraki örnekte, her öğe karşı temsilcisini yürütür bir Windows çalışma zamanı bileşeni ortak yönteminde özel temsilci bir istemci uygulaması geçirir bir `Vector`:  
  
 [!code-cpp[Cx_delegates#118](../cppcx/codesnippet/CPP/clientapp/mainpage.xaml.cpp#118)]  
  
 [!code-cpp[Cx_delegates#119](../cppcx/codesnippet/CPP/delegatesevents/class1.cpp#119)]  
  
### <a name="construction"></a>Yapı  
 Bu nesnelerin herhangi biri bir temsilciyi oluşturmak:  
  
-   lambda  
  
-   statik işlevi  
  
-   üye işaretçileri  
  
-   Std::Function  
  
 Aşağıdaki örnek, bu nesnelerin her biri bir temsilciyi oluşturmak gösterilmiştir. Tam olarak aynı şekilde, oluşturmak için kullanılan nesne türüne bakılmaksızın temsilcisi tüketebilir.  
  
 [!code-cpp[Cx_delegates#115](../cppcx/codesnippet/CPP/delegatesevents/class1.cpp#115)]  
  
> [!WARNING]
>  "Bu" işaretçiyi yakalayan bir lambda kullanırsanız, kullandığınızdan emin olun `-=` lambda çıkmadan önce olaydan açıkça kaydını işleci. Daha fazla bilgi için bkz: [olayları](../cppcx/events-c-cx.md).  
  
### <a name="generic-delegates"></a>Genel temsilciler  
 Genel temsilciler C + +/ CX Genel sınıflar bildirimleri için benzer kısıtlamaları vardır. Bunlar genel olarak bildirilemez. Özel bildirebilir iç genel temsilci ve C++ ancak .NET kullanabilir veya .winmd meta verileri yayılan değil çünkü JavaScript istemciler bunu kullanamayacaklarını. Bu örnek yalnızca C++ tarafından kullanılan genel bir temsilci bildirir:  
  
 [!code-cpp[Cx_delegates#116](../cppcx/codesnippet/CPP/delegatesevents/class1.h#116)]  
  
 Sonraki örnek bir sınıf tanımı içinde temsilci özelleştirilmiş bir örneğini bildirir:  
  
 [!code-cpp[Cx_delegates#117](../cppcx/codesnippet/CPP/delegatesevents/class1.h#117)]  
  
## <a name="delegates-and-threads"></a>Temsilciler ve iş parçacıkları  
 İşlev nesnesi gibi bir temsilci gelecekte bir zamanda yürütecek kodunu içerir. Oluşturur ve temsilci ve kabul eder ve temsilci yürüten işlev aktaran kodu aynı iş parçacığı üzerinde çalıştırıyorsanız, ardından görece basit noktalardır. Bu iş parçacığı kullanıcı Arabirimi iş parçacığı ise temsilci doğrudan kullanıcı arabirimi nesneleri XAML denetimleri gibi yönetebilirsiniz.  
  
 Bir iş parçacıklı grupta çalıştırır ve bu bileşen için bir temsilci sağlayan bir Windows çalışma zamanı bileşeni bir istemci uygulaması yüklenirse, varsayılan olarak doğrudan STA iş parçacığı üzerinde temsilci çağrılır. Çoğu Windows çalışma zamanı bileşenleri STA veya MTA içinde çalıştırabilirsiniz.  
  
 Temsilci yürütülen kodunun farklı bir iş parçacığı üzerinde çalışıp çalışmadığını — Örneğin, bir concurrency::task nesne bağlamında — sonra Paylaşılan verilere erişimi eşitlemekten sorumludur. Örneğin, temsilciniz bir vektör başvuruyor ve XAML denetimi aynı vektör başvuruyor kilitlenmeleri veya temsilci ve XAML denetim vektör sam adresindeki erişmeyi denediğinde, ortaya çıkabilecek yarış durumları kaçınmak için adımları almalıdır e süre. Ayrıca temsilci temsilci çağrılmadan önce kapsamının dışına geçebilir başvuru yerel değişkenleri tarafından yakalama girişimi değil ilgilenebilmek gerekir.  
  
 Oluşturulan temsilciniz oluşturulduğu aynı iş parçacığı üzerinde geri çağrılması istiyorsanız — örneğin, bir MTA grupta çalıştıran bileşenine geçirirseniz — ve Oluşturucusu aynı parçacığında çağrılan istiyor , ardından ikinci bir alan temsilci oluşturucusu kullanın `CallbackContext` parametresi. Yalnızca bu kayıtlı bir proxy/stub sahip yetkililer kullanın; tüm Windows.winmd içinde tanımlanan temsilcileri kaydedilir.  
  
 Olay işleyicileri .NET içinde biliyorsanız, önerilen uygulama, yangın önce bir olay yerel bir kopyasını olduğunu biliyor. Bu olay yalnızca çağrılmadan önce olay işleyici kaldırılabilir yarış durumları önler. C + bunun gerekli değildir +/ CX olay işleyicileri zaman eklendiğinde veya kaldırıldığında olduğundan yeni bir işleyici listesi oluşturulur. Bir olay çağırmadan önce başvuru sayısı işleyici listesinde bir C++ nesnesi artırması nedeniyle, tüm işleyiciler geçerli olacağını garanti edilir. Ancak, bu da Süren iş parçacığı üzerinde bir olay işleyicisi kaldırırsanız, yayımlama nesne artık güncel değil listesinde kopyasını üzerinde çalışıyorsa bu işleyici hala çağrılan, anlamına gelir. Yayımlama nesne, olay harekete zamana kadar güncelleştirilmiş listesini almazsınız.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tür sistemi](../cppcx/type-system-c-cx.md)   
 [Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)   
 [Ad alanları başvurusu](../cppcx/namespaces-reference-c-cx.md)