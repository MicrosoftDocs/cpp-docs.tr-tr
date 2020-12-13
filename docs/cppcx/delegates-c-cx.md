---
description: 'Daha fazla bilgi edinin: Temsilciler (C++/CX)'
title: Temsilciler (C++/CX)
ms.date: 01/22/2017
ms.assetid: 3175bf1c-86d8-4eda-8d8f-c5b6753d8e38
ms.openlocfilehash: 3d62b48d76319d79707330e874e6ceddcc22284e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342016"
---
# <a name="delegates-ccx"></a>Temsilciler (C++/CX)

**`delegate`** Anahtar sözcüğü, standart C++ içindeki bir işlev nesnesinin Windows çalışma zamanı eşdeğeri olan bir başvuru türü bildirmek için kullanılır. Bir işlev imzasına benzer bir temsilci bildirimi; Sarmalanan işlevin sahip olması gereken dönüş türünü ve parametre türlerini belirtir. Bu, Kullanıcı tanımlı bir temsilci bildirimidir:

```cpp
public delegate void PrimeFoundHandler(int result);
```

Temsilciler, en yaygın olarak olaylar ile birlikte kullanılır. Bir olayın bir arabirim türüne sahip olduğu şekilde bir temsilci türü vardır. Temsilci, olay işleyicilerinin çok daha fazla karşılayan bir sözleşmeyi temsil eder. Aşağıda türü daha önceden tanımlanmış olan temsilci olan bir olay sınıfı üyesi verilmiştir:

```cpp
event PrimeFoundHandler^ primeFoundEvent;
```

Windows Çalışma Zamanı uygulama ikili arabirimindeki istemcilere sunulacak temsilcileri bildirirken [Windows:: Foundation:: TypedEventHandler \<TSender, TResult> ](/uwp/api/windows.foundation.typedeventhandler-2)kullanın. Bu temsilci, JavaScript istemcileri tarafından tüketilebilmesi için önceden tanımlanmış proxy ve saplama ikililerini içerir.

## <a name="consuming-delegates"></a>Temsilcileri kullanma

Bir Evrensel Windows Platformu uygulaması oluşturduğunuzda, genellikle bir Windows Çalışma Zamanı sınıfının açığa çıkardığı bir olayın türü olarak bir temsilciyle çalışırsınız. Bir olaya abone olmak için, temsilci imzasıyla eşleşen bir işlev (veya lambda) belirterek temsilci türünün bir örneğini oluşturun. Sonra, `+=` temsilci nesnesini sınıftaki olay üyesine iletmek için işlecini kullanın. Bu, olaya abone olma olarak bilinir. Sınıf örneği "tetiklendiğinde", işleviniz, nesneniz veya diğer nesneleriniz tarafından eklenen diğer işleyicilerle birlikte çağırılır.

> [!TIP]
> Bir olay işleyicisi oluşturduğunuzda Visual Studio sizin için çok sayıda iş yapar. Örneğin, XAML biçimlendirmesinde bir olay işleyicisi belirtirseniz bir araç ipucu görünür. Araç ipucunu seçerseniz, Visual Studio otomatik olarak olay işleyicisi yöntemini oluşturur ve yayımlama sınıfındaki olayla ilişkilendirir.

Aşağıdaki örnekte temel desenler gösterilmektedir. `Windows::Foundation::TypedEventHandler` temsilci türüdür. Handler işlevi adlandırılmış bir işlev kullanılarak oluşturulur.

App. h 'de:

[!code-cpp[cx_delegates#120](../cppcx/codesnippet/CPP/delegatesevents/class1.h#120)]

App. cpp içinde:

[!code-cpp[cx_delegates#121](../cppcx/codesnippet/CPP/delegatesevents/class1.cpp#121)]

> [!WARNING]
> Genel olarak, bir olay işleyicisi için, döngüsel başvurulardan kaçınmak için harika bir işlem yapmadığınız müddetçe lambda yerine adlandırılmış bir işlev kullanmak daha iyidir. Adlandırılmış bir işlev, zayıf başvuruya göre "This" işaretçisini yakalar, ancak bir lambda bunu güçlü başvuruya göre yakalar ve döngüsel bir başvuru oluşturur. Daha fazla bilgi için bkz. [zayıf başvurular ve ayırma döngüleri](../cppcx/weak-references-and-breaking-cycles-c-cx.md).

Kural gereği, Windows Çalışma Zamanı tarafından tanımlanan olay işleyicisi temsilci adları, * EventHandler biçiminde olur — Örneğin, RoutedEventHandler, SizeChangedEventHandler veya SuspendingEventHandler. Ayrıca kurala göre, olay işleyicisi temsilcileri iki parametreye sahiptir ve void döndürür. Tür parametrelerine sahip olmayan bir temsilci içinde, ilk parametre [Platform:: Object ^](../cppcx/platform-object-class.md); türünde Bu, olayı tetikleyen nesne olan gönderici için bir başvuru içerir. Olay işleyicisi yönteminde bağımsız değişkenini kullanmadan önce özgün türe dönüştürmeniz gerekir. Tür parametrelerine sahip bir olay işleyicisi temsilcisine, ilk tür parametresi gönderenin türünü belirtir ve ikinci parametre, olay hakkında bilgi tutan bir başvuru sınıfına yönelik bir tanıtıcıdır. Kurala göre, bu sınıf EventArgs olarak adlandırılır \* . Örneğin, bir RoutedEventHandler temsilcisinin RoutedEventArgs ^ türünde ikinci bir parametresi vardır ve Dragevenınder, DragEventArgs ^ türünde ikinci bir parametreye sahiptir.

Kural gereği, zaman uyumsuz bir işlem tamamlandığında yürütülen kodu saran * CompletedHandler olarak adlandırılan Temsilciler. Bu temsilciler, sınıf üzerinde olaylar olarak değil, özellikler olarak tanımlanır. Bu nedenle, bu `+=` işlece abone olmak için işlecini kullanamazsınız; yalnızca özelliğe bir temsilci nesnesi atarsınız.

> [!TIP]
> C++ IntelliSense tam temsilci imzasını göstermez; Bu nedenle, EventArgs parametresinin belirli bir türünü belirlemenize yardımcı olmaz. Türü bulmak için **nesne tarayıcısı** gidebilir ve `Invoke` temsilcinin yöntemine bakabilirsiniz.

## <a name="creating-custom-delegates"></a>Özel temsilciler oluşturma

Kendi temsilcilerinizi tanımlayabilir, olay işleyicilerini tanımlayabilir veya tüketicilerin Windows Çalışma Zamanı bileşeninizdeki özel işlevselliği geçmesini sağlayabilirsiniz. Diğer tüm Windows Çalışma Zamanı türleri gibi genel bir temsilci genel olarak bildirilemez.

### <a name="declaration"></a>Bildirim

Temsilcinin bildirimi, temsilci bir tür olması dışında işlev bildirimine benzer. Genellikle, bir temsilci bildirimini bir sınıf bildiriminde iç içe yayabilseniz de bir temsilciyi ad alanı kapsamında bildirirsiniz. Aşağıdaki temsilci, `ContactInfo^` girdi olarak alan ve döndüren tüm işlevleri Kapsüller `Platform::String^` .

[!code-cpp[cx_delegates#111](../cppcx/codesnippet/CPP/delegatesevents/class1.h#111)]

Bir temsilci türü bildirdikten sonra, bu türün veya bu türdeki nesneleri parametre olarak alan yöntemlerin sınıf üyelerini bildirebilirsiniz. Bir yöntem veya işlev, bir temsilci türü de döndürebilir. Aşağıdaki örnekte, `ToCustomString` yöntemi temsilciyi bir giriş parametresi olarak alır. Yöntemi, istemci kodunun bir nesnenin bazı veya tüm ortak özelliklerinden bir dize oluşturan özel bir işlev sağlamasına olanak sağlar `ContactInfo` .

[!code-cpp[Cx_delegates#112](../cppcx/codesnippet/CPP/delegatesevents/class1.h#112)]

> [!NOTE]
> Herhangi bir Windows Çalışma Zamanı başvuru türüyle yaptığınız gibi, temsilci türüne başvurduğunuzda "^" sembolünü kullanırsınız.

Olay bildiriminin her zaman bir temsilci türü vardır. Bu örnek, Windows Çalışma Zamanı tipik bir temsilci türü imzasını gösterir:

[!code-cpp[cx_delegates#122](../cppcx/codesnippet/CPP/delegatesevents/class1.h#122)]

`Click` `Windows:: UI::Xaml::Controls::Primitives::ButtonBase` Sınıftaki olay türündedir `RoutedEventHandler` . Daha fazla bilgi için bkz. [Olaylar](../cppcx/events-c-cx.md).

İstemci kodu önce kullanarak temsilci örneğini oluşturur `ref new` ve temsilci imzasıyla uyumlu bir lambda sağlar ve özel davranışı tanımlar.

[!code-cpp[Cx_delegates#113](../cppcx/codesnippet/CPP/delegatesevents/class1.cpp#113)]

Ardından üye işlevini çağırır ve temsilciyi geçirir. Bunun `ci` bir örnek olduğunu `ContactInfo^` ve bir xaml olduğunu varsayalım `textBlock` `TextBlock^` .

[!code-cpp[Cx_delegates#114](../cppcx/codesnippet/CPP/delegatesevents/class1.cpp#114)]

Bir sonraki örnekte, bir istemci uygulaması özel bir temsilciyi bir Windows Çalışma Zamanı bileşeninde ortak bir yönteme geçirir ve bu her bir öğeye karşı temsilciyi yürütür `Vector` :

[!code-cpp[Cx_delegates#118](../cppcx/codesnippet/CPP/clientapp/mainpage.xaml.cpp#118)]

[!code-cpp[Cx_delegates#119](../cppcx/codesnippet/CPP/delegatesevents/class1.cpp#119)]

### <a name="construction"></a>İnşaat

Bu nesnelerden herhangi birinden bir temsilci oluşturabilirsiniz:

- lambda

- static işlevi

- üye işaretçisi

- std:: işlevi

Aşağıdaki örnek, bu nesnelerden her bir temsilcinin nasıl oluşturulduğunu gösterir. Temsilciyi, onu oluşturmak için kullanılan nesne türüne bakılmaksızın tamamen aynı şekilde kullanırsınız.

[!code-cpp[Cx_delegates#115](../cppcx/codesnippet/CPP/delegatesevents/class1.cpp#115)]

> [!WARNING]
> "This" işaretçisini yakalayan bir lambda kullanırsanız, `-=` lambda 'den çıkmadan önce olaydan açıkça kaydını silmek için işlecini kullandığınızdan emin olun. Daha fazla bilgi için bkz. [Olaylar](../cppcx/events-c-cx.md).

### <a name="generic-delegates"></a>Genel temsilciler

C++/CX içindeki genel temsilcilerin genel sınıfların bildirimlerine benzer kısıtlamalar vardır. Bunlar ortak olarak bildirilemez. Özel veya iç genel bir temsilci bildirebilir ve bunu C++ ' dan kullanabilirsiniz, ancak .NET veya JavaScript istemcileri. winmd meta verilerine yayılmadığından onu tüketemez. Bu örnek, yalnızca C++ tarafından tüketilen genel bir temsilci bildirir:

[!code-cpp[Cx_delegates#116](../cppcx/codesnippet/CPP/delegatesevents/class1.h#116)]

Sonraki örnek, bir sınıf tanımı içinde temsilcinin özelleşmiş bir örneğini bildirir:

[!code-cpp[Cx_delegates#117](../cppcx/codesnippet/CPP/delegatesevents/class1.h#117)]

## <a name="delegates-and-threads"></a>Temsilciler ve iş parçacıkları

Bir işlev nesnesi gibi bir temsilci, gelecekte bir zamanda yürütülecek kodu içerir. Temsilciyi oluşturan ve geçiren kod ve temsilciyi kabul eden ve yürüten işlev aynı iş parçacığında çalışıyorsa, oldukça basittir. Bu iş parçacığı UI iş parçacığı ise, temsilci XAML denetimleri gibi kullanıcı arabirimi nesnelerini doğrudan işleyebilir.

Bir istemci uygulaması, iş parçacıklı grupta çalışan bir Windows Çalışma Zamanı bileşeni yüklerse ve bu bileşene bir temsilci sağlıyorsa, varsayılan olarak, temsilci doğrudan STA iş parçacığında çağrılır. Çoğu Windows Çalışma Zamanı bileşen STA veya MTA 'da çalıştırılabilir.

Temsilciyi yürüten kod farklı bir iş parçacığında çalışıyorsa — Örneğin, concurrency:: Task nesnesi bağlamı içinde —, paylaşılan verilere erişimi eşitlemekten sorumludur. Örneğin, temsilciniz bir Vector öğesine başvuru içeriyorsa ve bir XAML denetiminin aynı vektöre bir başvurusu varsa, hem temsilci hem de XAML denetimi aynı anda vektöre erişmeyi denediklerinde oluşabilecek kilitlenmeleri veya yarış koşullarını önlemek için gerekli adımları uygulamanız gerekir. Ayrıca temsilcinin, temsilci çağrılmadan önce kapsam dışına gidebilecek başvuru yerel değişkenleri ile yakalamayı denemediğini de dikkate almalısınız.

Oluşturulan temsilcinin üzerinde oluşturulduğu iş parçacığında geri çağrılmasını istiyorsanız — Örneğin, bunu bir MTA grubu içinde çalışan bir bileşene geçirirseniz ve oluşturucunun aynı iş parçacığında çağrılmasını istiyorsanız, ikinci bir parametre alan temsilci Oluşturucu aşırı yüklemesini kullanın, ardından, `CallbackContext` Bu aşırı yüklemeyi yalnızca kayıtlı proxy/saplama olan Temsilcilerde kullanın; Windows. winmd 'de tanımlanan temsilcilerin hepsi kayıtlı değildir.

.NET ' te olay işleyicileri hakkında bilgi sahibiyseniz, başlamadan önce bir olayın yerel bir kopyasını oluşturmak için önerilen uygulama olduğunu bilirsiniz. Bu, olay bir işleyicinin Olay çağrılmadan hemen önce kaldırılabileceği yarış durumlarını önler. Olay işleyicileri eklendiğinde veya kaldırıldığında yeni bir işleyici listesi oluşturulduğunda bunu C++/CX ' te yapmak gerekli değildir. Bir C++ nesnesi bir olayı çağırmadan önce işleyici listesindeki başvuru sayısını artırdığından, tüm işleyicilerin geçerli olacağı garanti edilir. Bununla birlikte, bu durum, tüketim iş parçacığında bir olay işleyicisini kaldırırsanız, bu işleyicinin hala güncel olmayan bir liste Kopyasında hala çalışmaya devam ediyorsa, bu işleyicinin hala çağrılabilir durumda olabileceğini de unutmayın. Yayımlama nesnesi, olay bir sonraki sefer tetiklenene kadar güncelleştirilmiş listeyi almaz.

## <a name="see-also"></a>Ayrıca bkz.

[Tür sistemi](../cppcx/type-system-c-cx.md)<br/>
[C++/CX dil başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad alanı başvurusu](../cppcx/namespaces-reference-c-cx.md)
