---
title: Temsilciler (C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 3175bf1c-86d8-4eda-8d8f-c5b6753d8e38
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fda9cab73088746ec64caf482f9e606d713eaa4f
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43222749"
---
# <a name="delegates-ccx"></a>Temsilciler (C + +/ CX)
`delegate` Anahtar sözcüğü, bir işlev nesnesi standart C++'ta Windows çalışma zamanı eşdeğerdir bir başvuru türü bildirmek için kullanılır. Temsilci bildirimi için işlev imzasına benzer; Bu, sarmalanmış işlev olmalıdır parametre türleri ve dönüş türü belirtir. Bu kullanıcı tarafından tanımlanan temsilci bildirimi şu şekildedir:  
  
```cpp  
     public delegate void PrimeFoundHandler(int result);  
```  
  
 Temsilciler, olay ile birlikte en yaygın olarak kullanılır. Bir olay bir temsilci türü çok benzer bir sınıf bir arabirim türü olabilir aynı şekilde sahiptir. Temsilci, olay işleyicileri çok karşılayan bir sözleşmeyi temsil eder. Önceden tanımlanmış temsilci türü olan bir olay sınıf üyesi şu şekildedir:  
  
```cpp  
event PrimeFoundHandler^ primeFoundEvent;  
```  
  
 Windows çalışma zamanı uygulama ikili arabiriminde kullanıma sunulacak temsilciler istemcilere bildirirken kullanın [typedeventhandler\<TSender, TResult >](https://msdn.microsoft.com/library/windows/apps/br225997.aspx). Bu temsilci etkinleştirmediğiniz Javascript istemciler tarafından kullanılacak proxy ve saplama ikili dosyaları önceden tanımlanmış.  
  
## <a name="consuming-delegates"></a>Temsilcileri kullanma  
 Bir evrensel Windows platformu uygulaması oluşturduğunuzda, genellikle bir Windows çalışma zamanı sınıfı bir olay türü olarak bir temsilci ile çalışır. Bir olaya abone olmak için bir işlev belirterek, temsilci türünün bir örneği oluşturma — veya lambda —, temsilci imzasında eşleşir. Ardından `+=` temsilci nesne sınıfında olay üyeye geçirilecek işleci. Bu olaya abone olma olarak bilinir. Sınıf örneği "olay oluşturulduğunda", nesnenizin veya diğer nesneleri tarafından eklenen herhangi bir işleyicileri birlikte, işlev çağrılır.  
  
> [!TIP]
>  Bir olay işleyicisi oluşturduğunuzda, visual Studio birçok iş sizin için halleder. Örneğin, bir olay işleyicisi XAML biçimlendirmede belirtirseniz, araç ipucu görünür. Araç İpucu seçerseniz Visual Studio otomatik olarak olay işleyicisi yöntemi oluşturur ve yayımlama sınıfı olayı ile ilişkilendirir.  
  
 Aşağıdaki örnek, temel düzeni gösterir. `Windows::Foundation::TypedEventHandler` Temsilci türüdür. İşleyici işlevi, adlandırılmış bir işlevi kullanarak oluşturulur.  
  
 App.h içinde:  
  
 [!code-cpp[cx_delegates#120](../cppcx/codesnippet/CPP/delegatesevents/class1.h#120)]  
  
 App.cpp içinde:  
  
 [!code-cpp[cx_delegates#121](../cppcx/codesnippet/CPP/delegatesevents/class1.cpp#121)]  
  
> [!WARNING]
>  Genel olarak, bir olay işleyicisi için döngüsel başvuru kaçınmak için dikkatli almadıkları sürece, bir lambda yerine adlandırılmış bir işlev kullanılması daha iyidir. Adlandırılmış bir işlev tarafından zayıf başvuru "Bu" işaretçiyi yakalar, ancak bir lambda güçlü başvuruya göre yakalayan ve döngüsel bir başvuru oluşturur. Daha fazla bilgi için [zayıf başvurular ve döngüleri kesme](../cppcx/weak-references-and-breaking-cycles-c-cx.md).  
  
 Kural gereği, Windows çalışma zamanı tarafından tanımlanan olay işleyicisi temsilci adlarının biçimi şöyledir: * EventHandler — Örneğin, RoutedEventHandler, SizeChangedEventHandler veya SuspendingEventHandler. Ayrıca kural olarak, olay işleyici temsilcilerini iki parametreye sahiptir ve void döndürür. Türüdür ilk parametre tür parametrelerine sahip olmayan bir Temsilcide [Platform::Object ^](../cppcx/platform-object-class.md); olayı tetikleyen nesne gönderen bir başvuru içerir. Olay işleyicisi yönteminde bağımsız değişken kullanmadan önce yeniden orijinal türüne sahip. Tür parametreleri olan bir olay işleyici temsilcisini, gönderen türünü ilk tür parametresi belirtir ve ikinci parametresi olayla ilgili bilgileri içeren bir başvuru sınıfı için bir tanıtıcı. Kural olarak, bu sınıf adlı \*EventArgs. Örneğin, bir RoutedEventHandler temsilci RoutedEventArgs türünde ikinci bir parametresi vardır ^, ve DragEventHander DragEventArgs türünde ikinci bir parametre ^.  
  
 Kural gereği, zaman uyumsuz bir işlem tamamlandığında yürütülen kod kaydırma temsilciler adlandırılır * CompletedHandler. Bu temsilciler sınıfındaki özellikleri olmayan olaylar olarak tanımlanır. Bu nedenle, kullanmadığınız `+=` abone olursanız; için işleci yalnızca bir temsilci nesnesinin özelliğine atayın.  
  
> [!TIP]
>  C++ IntelliSense, tüm temsilci imzasında göstermez; Bu nedenle, bu belirli türde bir EventArgs parametresi belirlemenize yardımcı olmaz. Tür bulmak için giderek **Nesne Tarayıcısı** bakın `Invoke` temsilci için yöntemi.  
  
## <a name="creating-custom-delegates"></a>Özel temsilci oluşturma  
 Olay işleyicilerini tanımlamak için veya özel işlevler için Windows çalışma zamanı bileşeni geçmesine olanak sağlamak için kendi temsilcileri tanımlayabilirsiniz. Diğer Windows çalışma zamanı türü gibi genel temsilci genel'olarak bildirilemez.  
  
### <a name="declaration"></a>Bildirim  
 Temsilci bildirimi temsilci türü olan bir işlev bildirimi benzer. Genellikle, ayrıca bir sınıf bildiriminde bir temsilci bildirimini iç içe yerleştirebilseniz ad alanı kapsamında bir temsilci bildirin. Aşağıdaki temsilci isteyen herhangi bir işlevi kapsülleyen bir `ContactInfo^` giriş ve döndürür olarak bir `Platform::String^`.  
  
 [!code-cpp[cx_delegates#111](../cppcx/codesnippet/CPP/delegatesevents/class1.h#111)]  
  
 Bir temsilci türü bildirdikten sonra sınıf üyeleri, tür veya bu tür nesneleri parametre olarak geçirmesine yöntemleri bildirebilirsiniz. Ayrıca, bir yöntem veya işlev temsilci türü döndürebilir. Aşağıdaki örnekte, `ToCustomString` yöntemi temsilci giriş parametresi olarak alır. Yöntem bir dizeden bazılarını veya tümünü genel özelliklerini oluşturan özel bir işlev sağlamak istemci kodu sağlar bir `ContactInfo` nesne.  
  
 [!code-cpp[Cx_delegates#112](../cppcx/codesnippet/CPP/delegatesevents/class1.h#112)]  
  
> [!NOTE]
>  Kullandığınız "^" sembol temsilci türüne başvurduğunuzda türü ile herhangi bir Windows çalışma zamanı yalnızca başvuru olarak.  
  
 Her zaman bir olay bildirimi, bir temsilci türü vardır. Bu örnek, tipik bir temsilci gösterir. Windows çalışma zamanı tür imzası:  
  
 [!code-cpp[cx_delegates#122](../cppcx/codesnippet/CPP/delegatesevents/class1.h#122)]  
  
 `Click` Olayında `Windows:: UI::Xaml::Controls::Primitives::ButtonBase` sınıf türüdür `RoutedEventHandler`. Daha fazla bilgi için [olayları](../cppcx/events-c-cx.md).  
  
 İstemci kodu ilk kullanarak temsilci örneği oluşturur `ref new` ve temsilci imzası ile uyumludur ve özel durum tanımlayan bir lambda sağlama.  
  
 [!code-cpp[Cx_delegates#113](../cppcx/codesnippet/CPP/delegatesevents/class1.cpp#113)]  
  
 Üye işlevini çağırır ve temsilci geçirir. Varsayımında `ci` olduğu bir `ContactInfo^` örneği ve `textBlock` olan bir XAML `TextBlock^`.  
  
 [!code-cpp[Cx_delegates#114](../cppcx/codesnippet/CPP/delegatesevents/class1.cpp#114)]  
  
 Sonraki örnekte, bir istemci uygulama bir genel yöntem, her öğe karşı temsilci yürüten bir Windows çalışma zamanı bileşeni için özel bir temsilci geçirir bir `Vector`:  
  
 [!code-cpp[Cx_delegates#118](../cppcx/codesnippet/CPP/clientapp/mainpage.xaml.cpp#118)]  
  
 [!code-cpp[Cx_delegates#119](../cppcx/codesnippet/CPP/delegatesevents/class1.cpp#119)]  
  
### <a name="construction"></a>Oluşturma  
 Bu nesnelerin herhangi bir temsilci oluşturabilirsiniz:  
  
-   lambda  
  
-   statik işlevi  
  
-   işaretçi-üye  
  
-   Std::Function  
  
 Aşağıdaki örnek, bu nesnelerin her biri bir temsilciyi oluşturmak gösterilmektedir. Temsilci, onu oluşturmak için kullanılan nesne türü ne olursa olsun tam olarak aynı şekilde kullanır.  
  
 [!code-cpp[Cx_delegates#115](../cppcx/codesnippet/CPP/delegatesevents/class1.cpp#115)]  
  
> [!WARNING]
>  "Bu" işaretçiyi yakalayan bir lambda kullanırsanız, kullandığınızdan emin olun `-=` lambda çıkmadan önce bu olaydan açıkça kaydını işleci. Daha fazla bilgi için [olayları](../cppcx/events-c-cx.md).  
  
### <a name="generic-delegates"></a>Genel temsilciler  
 Genel temsilciler C + +/ CX genel sınıf bildirimleri için benzer kısıtlamalar vardır. Bunlar genel olarak bildirilemez. Özel bir bildirebilirsiniz iç genel temsilci ve C++, ancak .NET kullanma veya .winmd meta verilere yayılır değil çünkü JavaScript istemciler bunu kullanamıyor. Bu örnek yalnızca C++ tarafından tüketilebilecek bir genel temsilci bildirir:  
  
 [!code-cpp[Cx_delegates#116](../cppcx/codesnippet/CPP/delegatesevents/class1.h#116)]  
  
 Sonraki örnek, bir sınıf tanımı içinde bir temsilci özelleşmiş bir örneğini bildirir:  
  
 [!code-cpp[Cx_delegates#117](../cppcx/codesnippet/CPP/delegatesevents/class1.h#117)]  
  
## <a name="delegates-and-threads"></a>Temsilciler ve iş parçacıkları  
 Bir işlev nesnesi gibi bir temsilci, gelecekte bir zamanda yürütülen kodu içerir. Ardından oluşturur ve temsilci ve kabul eder ve temsilci yürüten işlev kodu aynı iş parçacığı üzerinde çalışıyorsa, şeyler oldukça basittir. Bu iş parçacığı UI iş parçacığı ise, temsilci doğrudan XAML denetimleri gibi kullanıcı arabirimi nesneleri değiştirebilirsiniz.  
  
 Bir istemci uygulama bir iş parçacıklı apartmanda çalıştırır ve bu bileşene bir temsilci sağlayan bir Windows çalışma zamanı bileşeni yüklenirse, varsayılan olarak temsilci doğrudan STA iş parçacığı üzerinde çağrılır. Çoğu Windows çalışma zamanı bileşenleri STA veya MTA içinde çalıştırabilirsiniz.  
  
 Temsilci yürütülen kod farklı bir iş parçacığı üzerinde çalışıp çalışmadığı — Örneğin, bir concurrency::task nesne bağlamında — Paylaşılan verilere erişimi eşitlemek için sorumlu olursunuz. Örneğin, temsilciniz bir vektör başvuru içeriyor ve bir XAML denetimi başvuru aynı vektör varsa, kilitlenmeleri veya temsilci hem XAML denetimi sam vektörünü erişmeyi denediğinde ortaya çıkabilecek yarış durumlarını kaçınmak için gerekli adımları atmanız e zaman. Size de temsilci metot temsilcisinin çağrılmadan önce kapsam dışına geçebilir başvuru yerel değişkenler yakalama çalışmaz ilgileniriz gerekir.  
  
 Oluşturulan temsilciniz oluşturulmuş olan aynı iş parçacığında aranmak istiyorsanız — örneğin, bir MTA grupta çalışan bir bileşen için geçirirseniz — ve oluşturucusu olarak aynı iş parçacığında çağrılan istediğiniz , ardından ikinci bir alan temsilci oluşturucu aşırı yüklemesini kullanın `CallbackContext` parametresi. Yalnızca bu aşırı yükleme kayıtlı bir proxy/saplama sahip yetkililer kullanın. tüm Windows.winmd'i içinde tanımlanan temsilcileri kaydedilir.  
  
 . NET'te olay işleyicileri varsa, bir olay harekete, önce yerel bir kopyasını oluşturmak için önerilen uygulama olduğunu biliyorsunuz. Bu yalnızca olay çağrılmadan önce bir olay işleyicisi kaldırılabilir yarış durumları ortadan kaldırır. C +'da bunun gerekli değildir +/ CX olay işleyicileri zaman eklendiğinde veya kaldırıldığında olduğundan yeni bir işleyici listesi oluşturulur. Bir olay çağırmadan önce bir C++ nesnesi işleyicisi başvuru sayısını artırır çünkü tüm işleyiciler geçerli olacağı garanti edilir. Ancak, bu da tüketim iş parçacığı üzerinde bir olay işleyicisi kaldırırsanız, yayımlama nesnesi, artık güncel olmayan listenin kopyası üzerinde çalışıyorsa bu işleyici hala çağrılan, anlamına gelir. Yayımlama nesne, sonraki açışınızda kadar olayı tetikler güncelleştirilmiş listesini almazsınız.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tür sistemi](../cppcx/type-system-c-cx.md)   
 [Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)   
 [Ad alanları başvurusu](../cppcx/namespaces-reference-c-cx.md)