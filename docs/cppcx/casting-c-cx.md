---
title: Atama (C++/CX)
ms.date: 06/19/2018
ms.assetid: 5247f6c7-6a0a-4021-97c9-21c868bd9455
ms.openlocfilehash: 6711320fd9ca52360f702e029fdc8e129c90c6cd
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740533"
---
# <a name="casting-ccx"></a>Atama (C++/CX)

Dört farklı atama işleci Windows Çalışma Zamanı türleri için geçerlidir: [Static_cast işleci](../cpp/static-cast-operator.md), [dynamic_cast Işleci](../cpp/dynamic-cast-operator.md), **safe_cast işleci**ve [reinterpret_cast işleci](../cpp/reinterpret-cast-operator.md). **safe_cast** ve **static_cast** , dönüştürme gerçekleştirilemediği zaman bir özel durum oluşturur; [Static_cast işleci](../cpp/static-cast-operator.md) derleme zamanı tür denetimi de gerçekleştirir. **dynamic_cast** , türü dönüştüremediğinde **nullptr** ' i döndürür. **Reinterpret_cast** null olmayan bir değer döndürse de geçersiz olabilir. Bu nedenle, dönüştürmenin başarılı olacağını bilmiyorsanız **reinterpret_cast** 'yi kullanmanızı öneririz. Ayrıca, C++ **reinterpret_cast**kodunuzla aynı olduklarından,/CX kodunuzda C stili yayınları kullanmanızı öneririz.

Derleyici ve çalışma zamanı, bir değer türü veya yerleşik tür bağımsız değişken olarak parametre türü `Object^`olan bir yönteme geçirildiğinde de örtük yayınlar gerçekleştirir — Örneğin, kutulama işlemleri. Teorik olarak, örtük bir dönüştürme çalışma zamanında bir özel duruma asla neden olmaz; derleyici örtük bir dönüştürme gerçekleştiremediğinde, derleme zamanında bir hata oluşturur.

Windows Çalışma Zamanı, özel durumlar yerine HRESULT hata kodları kullanan COM üzerinden soyutlamadır. Genel olarak, [Platform:: InvalidCastException](../cppcx/platform-invalidcastexception-class.md) , E_NOINTERFACE alt düzey com hatası olduğunu gösterir.

## <a name="static_cast"></a>gerektiriyor

İki tür arasında bir devralma ilişkisi olup olmadığını anlamak için bir **static_cast** derleme zamanında denetlenir. Türler ilgili değilse, atama derleyici hatasına neden olur.

Başvuru sınıfındaki bir **static_cast** Ayrıca çalışma zamanı denetiminin gerçekleştirilmesine neden olur. Bir başvuru sınıfındaki bir **static_cast** derleme zamanı doğrulaması geçirebilir, ancak hala çalışma zamanında başarısız olur; Bu durumda bir `Platform::InvalidCastException` oluşturulur. Genel olarak, neredeyse her zaman geliştirme ve test sırasında ortadan kaldırabildiğiniz programlama hatalarını belirttiğinden, bu özel durumları işlemek zorunda kalmazsınız.

Kod iki tür arasında açıkça bir ilişki bildirirse **static_cast** kullanın ve bu nedenle dönüştürmenin çalışması için emin olun.

```cpp
    interface class A{};
    public ref class Class1 sealed : A { };
    // ...
    A^ obj = ref new Class1(); // Class1 is an A
    // You know obj is a Class1. The compiler verifies that this is possible, and in C++/CX a run-time check is also performed.
    Class1^ c = static_cast<Class1^>(obj);
```

## <a name="safe_cast"></a>safe_cast

**Safe_cast** işleci Windows çalışma zamanı bir parçasıdır. Çalışma zamanı tür denetimi gerçekleştirir ve dönüştürme başarısız olursa bir `Platform::InvalidCastException` oluşturur. Bir çalışma zamanı hatası olağanüstü bir koşulu gösteriyorsa, **safe_cast** kullanın. **Safe_cast** 'in birincil amacı, geliştirme ve test aşamaları sırasında ortaya çıkabilecek bir noktada programlama hatalarının tanımlanmasına yardımcı olur. İşlenmeyen özel durumun kendi hata noktasını tanımladığı için özel durumu işlemek zorunda değilsiniz.

Kod ilişkiyi bildirmiyorsa ancak dönüştürmenin çalışması için safe_cast kullanın.

```cpp
    // A and B are not related
    interface class A{};
    interface class B{};
    public ref class Class1 sealed : A, B { };
    // ...
    A^ obj = ref new Class1();

    // You know that obj’s backing type implements A and B, but
    // the compiler can’t tell this by comparing A and B. The run-time type check succeeds.
    B^ obj2 = safe_cast<B^>(obj);
```

## <a name="dynamic_cast"></a>dynamic_cast

Daha türetilmiş bir türe bir nesne (özellikle, bir hat **^** ) aktardığınızda dynamic_cast kullanın, hedef nesnenin bazen **nullptr** olabileceğini veya dönüştürme işlemi başarısız olabileceğini ve bu koşulu bir özel durum yerine normal kod yolu. Örneğin, **boş uygulama (Evrensel Windows)** proje şablonunda, `OnLaunched` App. XAMP. cpp yöntemi uygulama penceresinde içerik olup olmadığını test etmek için **dynamic_cast** kullanır. İçerik yoksa bir hata değildir; beklenen bir durumdur. `Windows::Current::Content`, bir `Windows::UI::XAML::UIElement` ve dönüştürme, devralma hiyerarşisinde daha `Windows::UI.XAML::Controls::Frame`fazla türetilmiş bir tür olan öğesine.

```cpp
void App::OnLaunched(Windows::ApplicationModel::Activation::LaunchActivatedEventArgs^ args)
{
    auto rootFrame = dynamic_cast<Frame^>(Window::Current->Content);

    // Do not repeat app initialization when the window already has content,
    // just ensure that the window is active
    if (rootFrame == nullptr)
    {
        // Create a Frame to act as the navigation context and associate it with
        // a SuspensionManager key
        rootFrame = ref new Frame();
        // ...
    }
}
```

Başka bir **dynamic_cast** kullanımı, bir paketlenmiş değer `Object^` türü içerip içermediğini belirlemede bir araştırma belirlemektir. Bu durumda, bir `dynamic_cast<Platform::Box>` veya ' a `dynamic_cast<Platform::IBox>`kalkışın.

## <a name="dynamic_cast-and-tracking-references-"></a>dynamic_cast ve izleme başvuruları (%)

İzleme başvurusuna bir **dynamic_cast** de uygulayabilirsiniz, ancak bu durumda Cast **safe_cast**gibi davranır. Bir izleme `Platform::InvalidCastException` başvurusunun bir **nullptr**değeri olmadığı için hata oluşturur.

## <a name="reinterpret_cast"></a>reinterpret_cast

Ne bir derleme zamanı denetimi ne de bir çalışma zamanı denetimi gerçekleştirilmediğinden [reinterpret_cast](../cpp/reinterpret-cast-operator.md) kullanmanız önerilir. En kötü durumda, **reinterpret_cast** , programlama hatalarının geliştirme zamanında algılanmamasına ve programınızın davranışında kötü veya çok zararlı hatalara neden olmasına olanak sağlar. Bu nedenle, yalnızca ilgisiz türler arasında atama yapmanız gereken ancak dönüştürmenin başarılı olacağını bildiğiniz durumlarda **reinterpret_cast** kullanmanız önerilir. Nadiren kullanılan bir örnek, bir Windows Çalışma Zamanı türünü temel alınan ABı türüne dönüştürmelidir; Yani, nesne için başvuru saymasının denetimini alıyorsunuz. Bunu yapmak için [ComPtr sınıfı](../cpp/com-ptr-t-class.md) akıllı işaretçisini kullanmanızı öneririz. Aksi halde, arabirimde sürümü özel olarak çağırmanız gerekir. Aşağıdaki örnek, bir başvuru sınıfının bir `IInspectable*`öğesine nasıl yayınlankullanılabileceğini gösterir.

```cpp
#include <wrl.h>
using namespace Microsoft::WRL;
auto winRtObject = ref new SomeWinRTType();
ComPtr<IInspectable> inspectable = reinterpret_cast<IInspectable*>(winRtObject);
// ...
```

OneWindows çalışma zamanı arabiriminden diğerine dönüştürmek için **reinterpret_cast** kullanırsanız, nesnenin iki kez serbest bırakılması gerekir. Bu nedenle, yalnızcaC++ bileşen olmayan uzantılar arabirimine dönüştürme yaparken bu dönüştürmeyi kullanın.

## <a name="abi-types"></a>ABı türleri

- ABı türler Windows SDK üst bilgilerde canlı. Uygun şekilde, üst bilgiler ad alanlarından sonra adlandırılır — örneğin, `windows.storage.h`.

- ABı türler ABı — Örneğin, `ABI::Windows::Storage::Streams::IBuffer*`özel bir ad alanı içinde canlı.

- Windows çalışma zamanı arabirim türü ile eşdeğer ABI türü arasındaki Dönüşümler her zaman güvenlidir — Yani, `IBuffer^`. `ABI::IBuffer*`

- Bir Windows çalışma zamanı çalışma zamanı sınıfı, biliniyorsa, her `IInspectable*` zaman varsayılan arabirimine dönüştürülmelidir.

- ABı türlerine dönüştürdükten sonra, türün yaşam süresi ve COM kurallarını izlemeniz gerekir. ABI işaretçilerinin ömür yönetimini basitleştirmek `WRL::ComPtr` için kullanmanızı öneririz.

Aşağıdaki tabloda, **reinterpret_cast**kullanmanın güvenli olduğu durumlar özetlenmektedir. Her durumda, her iki yönde de atama güvenlidir.

|||
|-|-|
|`HSTRING`|`String^`|
|`HSTRING*`|`String^*`|
|`IInspectable*`|`Object^`|
|`IInspectable**`|`Object^*`|
|`IInspectable-derived-type*`|`same-interface-from-winmd^`|
|`IInspectable-derived-type**`|`same-interface-from-winmd^*`|
|`IDefault-interface-of-RuntimeClass*`|`same-RefClass-from-winmd^`|
|`IDefault-interface-of-RuntimeClass**`|`same-RefClass-from-winmd^*`|

## <a name="see-also"></a>Ayrıca bkz.

- [Tür Sistemi](../cppcx/type-system-c-cx.md)
- [C++/CX Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)
- [Ad Alanları Başvurusu](../cppcx/namespaces-reference-c-cx.md)
