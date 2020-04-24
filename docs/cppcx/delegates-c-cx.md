---
title: Temsilciler (C++/CX)
ms.date: 01/22/2017
ms.assetid: 3175bf1c-86d8-4eda-8d8f-c5b6753d8e38
ms.openlocfilehash: e570acafb8cce8b9496b79a062c3035015ba9811
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032479"
---
# <a name="delegates-ccx"></a>Temsilciler (C++/CX)

Anahtar `delegate` kelime, standart C++'daki bir işlev nesnesinin Windows Runtime eşdeğeri olan bir başvuru türünü bildirmek için kullanılır. İşlev imzasına benzer bir temsilci bildirimi; sarılmış işlevinin sahip olması gereken dönüş türünü ve parametre türlerini belirtir. Bu, kullanıcı tanımlı bir temsilci bildirimidir:

```cpp
public delegate void PrimeFoundHandler(int result);
```

Temsilciler en sık olaylarla birlikte kullanılır. Bir olay, bir sınıfın arabirim türüne sahip olabileceği gibi bir temsilci türüne sahiptir. Temsilci, olay işleyicilerinin çok fazla yerine getirdiği bir sözleşmeyi temsil eder. Türü daha önce tanımlanmış temsilci olan bir olay sınıfı üyesi aşağıda veda edebilirsiniz:

```cpp
event PrimeFoundHandler^ primeFoundEvent;
```

Windows Runtime uygulama ikili arabirimi genelinde istemcilere maruz kalacak temsilcileri bildirirken, [Windows kullanın::Foundation::TypedEventHandler\<TSender, TResult>](/uwp/api/windows.foundation.typedeventhandler-2). Bu temsilci, Javascript istemcileri tarafından tüketilmesini sağlayan proxy ve saplama ikililerini önceden tanımlamıştır.

## <a name="consuming-delegates"></a>Temsilcilerin tüketilmesi

Evrensel Windows Platformu uygulaması oluşturduğunuzda, genellikle bir Windows Runtime sınıfının ortaya çıkardığı bir olay türü olarak bir temsilciyle çalışırsınız. Bir etkinliğe abone olmak için, temsilci imzasıyla eşleşen bir işlev veya lambda belirterek temsilci türünden bir örnek oluşturun. Ardından, `+=` temsilci nesnesini sınıftaki olay üyesine geçirmek için işleci kullanın. Bu, olaya abone olmak olarak bilinir. Sınıf örneği olayı "ateşlediğinde" işleviniz, nesneniz veya diğer nesneler tarafından eklenen diğer işleyicilerle birlikte çağrılır.

> [!TIP]
> Visual Studio, bir etkinlik işleyicisi oluşturduğunuzda sizin için çok çalışır. Örneğin, XAML biçimlendirmesinde bir olay işleyicisi belirtirseniz, bir araç ipucu görüntülenir. Araç ipucunu seçerseniz, Visual Studio otomatik olarak olay işleyicisi yöntemini oluşturur ve yayımlama sınıfındaki olayla ilişkilendirir.

Aşağıdaki örnek, temel deseni gösterir. `Windows::Foundation::TypedEventHandler`temsilci türüdür. İşleyici işlevi adlandırılmış bir işlev kullanılarak oluşturulur.

App.h olarak:

[!code-cpp[cx_delegates#120](../cppcx/codesnippet/CPP/delegatesevents/class1.h#120)]

App.cpp olarak:

[!code-cpp[cx_delegates#121](../cppcx/codesnippet/CPP/delegatesevents/class1.cpp#121)]

> [!WARNING]
> Genel olarak, bir olay işleyicisi için, dairesel başvurulardan kaçınmaya büyük özen sürece lambda yerine adlandırılmış bir işlev kullanmak daha iyidir. Adlandırılmış bir işlev zayıf başvuru yla "bu" işaretçiyi yakalar, ancak bir lambda onu güçlü bir başvuruyla yakalar ve dairesel bir başvuru oluşturur. Daha fazla bilgi için [Zayıf başvurular ve kesme döngüleri'ne](../cppcx/weak-references-and-breaking-cycles-c-cx.md)bakın.

Kural kuralına göre, Windows Runtime tarafından tanımlanan olay işleyicisi temsilci adları *EventHandler-örneğin RoutedEventHandler, SizeChangedEventHandler veya AskıyaEventHandler formuna sahiptir. Ayrıca, olay işleyicisi delegeleriki parametre ve dönüş geçersiz vardır. Tür parametreleri olmayan bir temsilcide, ilk parametre tür [Platformu'dur::Object^](../cppcx/platform-object-class.md); gönderene bir başvuru tutar, bu da olayı ateşleyen nesnedir. Olay işleyicisi yönteminde bağımsız değişkeni kullanmadan önce özgün türe geri döküm gerekir. Tür parametreleri olan bir olay işleyicisi temsilcisinde, ilk tür parametresi gönderenin türünü belirtir ve ikinci parametre olay hakkında bilgi tutan bir ref sınıfının tanıtıcısI olur. Sözleşmeye göre, bu \*sınıfın adı EventArgs'dır. Örneğin, RoutedEventHandler temsilcisinin Ikinci bir parametresi RoutedEventArgs^, DragEventHander'ın ise DragEventArgs^ türünden ikinci bir parametresi vardır.

Kural olarak, eşil bir işlem tamamlandığında çalıştıran kodu sarın temsilcilere *CompletedHandler adı verilir. Bu temsilciler, olaylar olarak değil, sınıftaki özellikler olarak tanımlanır. Bu nedenle, `+=` operatöre abone olmak için kullanmayın; yalnızca bir temsilci nesnesi atayabilirsin.

> [!TIP]
> C++ IntelliSense tam temsilci imzasını göstermez; bu nedenle, EventArgs parametresinin belirli türünü belirlemenize yardımcı olmaz. Türü bulmak için **Nesne Tarayıcısı'na** gidebilir ve `Invoke` temsilci nin yöntemine bakabilirsiniz.

## <a name="creating-custom-delegates"></a>Özel temsilciler oluşturma

Olay işleyicilerini tanımlamak veya tüketicilerin Özel işlevler içinde Windows Runtime bileşeninize geçmesini sağlamak için kendi temsilcilerinizi tanımlayabilirsiniz. Diğer Windows Runtime türü gibi, genel bir temsilci genel olarak bildirilemez.

### <a name="declaration"></a>Bildirim

Temsilcinin bildirimi, temsilcinin bir tür olması dışında bir işlev bildirimine benzer. Genellikle, bir sınıf bildiriminde bir temsilci bildirimi nest edebilirsiniz, ancak ad alanı kapsamında bir temsilci bildirirsiniz. Aşağıdaki temsilci, bir girdi olarak alan `ContactInfo^` herhangi bir işlevi `Platform::String^`kapsüller ve bir .

[!code-cpp[cx_delegates#111](../cppcx/codesnippet/CPP/delegatesevents/class1.h#111)]

Bir temsilci türünü beyan ettikten sonra, bu tür sınıf üyelerini veya bu tür nesneleri parametre olarak alan yöntemleri bildirebilirsiniz. Bir yöntem veya işlev de bir temsilci türü döndürebilir. Aşağıdaki örnekte, `ToCustomString` yöntem bir giriş parametresi olarak temsilci alır. Yöntem, istemci kodunun bir `ContactInfo` nesnenin ortak özelliklerinin bir birinden veya tümünden bir dize oluşturan özel bir işlev sağlamasını sağlar.

[!code-cpp[Cx_delegates#112](../cppcx/codesnippet/CPP/delegatesevents/class1.h#112)]

> [!NOTE]
> Herhangi bir Windows Runtime başvuru türünde yaptığınız gibi, temsilci türüne atıfta bulunurken "^" simgesini kullanırsınız.

Olay bildiriminde her zaman bir temsilci türü vardır. Bu örnek, Windows Runtime'da tipik bir temsilci türü imzasını gösterir:

[!code-cpp[cx_delegates#122](../cppcx/codesnippet/CPP/delegatesevents/class1.h#122)]

Sınıftaki `Click` `Windows:: UI::Xaml::Controls::Primitives::ButtonBase` olay türündedir. `RoutedEventHandler` Daha fazla bilgi için [Etkinlikler'e](../cppcx/events-c-cx.md)bakın.

İstemci kodu önce temsilci `ref new` imzasıyla uyumlu bir lambda kullanarak ve sağlayarak ve özel davranışı tanımlayarak temsilci örneğini kurar.

[!code-cpp[Cx_delegates#113](../cppcx/codesnippet/CPP/delegatesevents/class1.cpp#113)]

Daha sonra üye işlevini çağırır ve temsilciyi geçer. Bunun `ci` bir `ContactInfo^` örnek `textBlock` olduğunu ve bir `TextBlock^`XAML olduğunu varsayalım.

[!code-cpp[Cx_delegates#114](../cppcx/codesnippet/CPP/delegatesevents/class1.cpp#114)]

Sonraki örnekte, istemci uygulaması, bir Windows Runtime bileşeninde, bir öğedeki her öğeye `Vector`karşı temsilciyi çalıştıran ortak bir metoduna özel bir temsilci geçer:

[!code-cpp[Cx_delegates#118](../cppcx/codesnippet/CPP/clientapp/mainpage.xaml.cpp#118)]

[!code-cpp[Cx_delegates#119](../cppcx/codesnippet/CPP/delegatesevents/class1.cpp#119)]

### <a name="construction"></a>İnşaat

Bu nesnelerden herhangi birinden bir temsilci oluşturabilirsiniz:

- lambda

- statik fonksiyon

- üyeye işaretçi

- std::fonksiyon

Aşağıdaki örnek, bu nesnelerin her birinden nasıl bir temsilci oluşturulabildiğini gösterir. Temsilciyi oluşturmak için kullanılan nesnenin türüne bakılmaksızın tam olarak aynı şekilde tüketirsiniz.

[!code-cpp[Cx_delegates#115](../cppcx/codesnippet/CPP/delegatesevents/class1.cpp#115)]

> [!WARNING]
> "Bu" işaretçisini yakalayan bir lambda kullanıyorsanız, lambda'dan çıkmadan önce olaydan kaydını açıkça geri almak için `-=` operatörü kullandığınızdan emin olun. Daha fazla bilgi için [Etkinlikler'e](../cppcx/events-c-cx.md)bakın.

### <a name="generic-delegates"></a>Genel temsilciler

C++/CX'teki genel temsilcilerin genel sınıf bildirimlerine benzer kısıtlamaları vardır. Bunlar halka açık olarak ilan edilemez. Özel veya dahili genel temsilciyi beyan edip C++'dan tüketebilirsiniz, ancak .NET veya JavaScript istemcileri .winmd meta verilerine yayılmayan için bu temsilciyi tüketemez. Bu örnek, yalnızca C++tarafından tüketilebilen genel bir temsilci bildirir:

[!code-cpp[Cx_delegates#116](../cppcx/codesnippet/CPP/delegatesevents/class1.h#116)]

Sonraki örnek, bir sınıf tanımı içinde temsilcinin özel bir örneğini bildirir:

[!code-cpp[Cx_delegates#117](../cppcx/codesnippet/CPP/delegatesevents/class1.h#117)]

## <a name="delegates-and-threads"></a>Temsilciler ve iş parçacıkları

Bir temsilci, tıpkı bir işlev nesnesi gibi, gelecekte bir zamanda yürütülecek kod içerir. Temsilciyi oluşturan ve geçen kod ve temsilciyi kabul eden ve yürüten işlev aynı iş parçacığı üzerinde çalışıyorsa, işler nispeten basittir. Bu iş parçacığı Kullanıcı Arabirimi iş parçacığı ise, temsilci doğrudan XAML denetimleri gibi kullanıcı arabirimi nesneleri işleyebilir.

Bir istemci uygulaması iş parçacığı apartmanında çalışan bir Windows Runtime bileşeni yükler ve bu bileşene bir temsilci sağlarsa, varsayılan olarak temsilci doğrudan STA iş parçacığına çağrılır. Çoğu Windows Runtime bileşeni STA veya MTA'da çalıştırılabilir.

Temsilciyi çalıştıran kod farklı bir iş parçacığı üzerinde çalışıyorsa (örneğin, eşzamanlılık:görev nesnesi) bağlamında paylaşılan verilere erişimi eşitlemekten siz sorumlusunuz. Örneğin, temsilciniz bir Vektöre bir başvuru içeriyorsa ve XAML denetiminde aynı Vektöre başvuruda bulunuyorsa, hem temsilci hem de XAML denetimi vektöre aynı anda erişmeye çalışırken oluşabilecek kilitlenmeleri veya yarış koşullarını önlemek için adımlar atmalısınız. Ayrıca, temsilcinin çağrıldıktan önce kapsam dışına çıkabilecek yerel değişkenleri referans olarak yakalamaya çalışmamasını da göz önünde bulundurmalısınız.

Oluşturulan temsilcinizin oluşturulduğu iş parçacığına geri çağrılmasını istiyorsanız(örneğin, mta dairesinde çalışan bir bileşene geçerseniz- ve oluşturucuyla aynı iş parçacığıüzerinde çağrılmasını istiyorsanız, ikinci `CallbackContext` bir parametre alan temsilci oluşturucu aşırı yüklemesini kullanın. Bu aşırı yükü yalnızca kayıtlı bir proxy/stub'u olan temsilcilerde kullanın; Windows.winmd'de tanımlanan delegelerin tümü kayıtlı değildir.

.NET'teki olay işleyicilerini biliyorsanız, önerilen uygulamanın bir olayı ateşlemeden önce yerel bir kopyasını yapmak olduğunu bilirsiniz. Bu, olay çağrılmadan hemen önce bir olay işleyicisinin kaldırılabileceği yarış koşullarını önler. Olay işleyicileri eklendiğinde veya kaldırıldığında yeni bir işleyici listesi oluşturulduğundan, bunu C++/CX'te yapmanız gerekmez. C++ nesnesi, bir olayı çağıran önce işleyici listesindeki başvuru sayısını artımladığından, tüm işleyicilerin geçerli olacağı garanti edilir. Ancak, bu aynı zamanda, tüketen iş parçacığı üzerinde bir olay işleyicisi kaldırırsanız, yayımlama nesnesi şimdi güncel olmayan listenin kopyası üzerinde çalışmaya devam ediyorsa, bu işleyicinin yine de çağrılabileceği anlamına gelir. Yayımlama nesnesi, olayı bir sonraki kez yayınlayana kadar güncelleştirilmiş listeyi almaz.

## <a name="see-also"></a>Ayrıca bkz.

[Tür Sistemi](../cppcx/type-system-c-cx.md)<br/>
[C++/CX Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ad Alanları Başvurusu](../cppcx/namespaces-reference-c-cx.md)
