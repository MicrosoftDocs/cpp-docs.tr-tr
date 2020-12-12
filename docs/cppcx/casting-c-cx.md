---
description: ': Atama hakkında daha fazla bilgi edinin (C++/CX)'
title: Atama (C++/CX)
ms.date: 06/19/2018
ms.assetid: 5247f6c7-6a0a-4021-97c9-21c868bd9455
ms.openlocfilehash: 90b9e90833acc14bcf76287b44f70fb914c7604a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190282"
---
# <a name="casting-ccx"></a>Atama (C++/CX)

Dört farklı atama işleci Windows Çalışma Zamanı türleri için geçerlidir: [Static_cast işleci](../cpp/static-cast-operator.md), [dynamic_cast Işleci](../cpp/dynamic-cast-operator.md), **safe_cast işleci** ve [reinterpret_cast işleci](../cpp/reinterpret-cast-operator.md). **safe_cast** ve **`static_cast`** dönüştürme gerçekleştirilemediği zaman bir özel durum oluşturur; [Static_cast işleci](../cpp/static-cast-operator.md) de derleme zamanı tür denetimi gerçekleştirir. **`dynamic_cast`****`nullptr`** türü dönüştüremezse döndürür. **`reinterpret_cast`** Null olmayan bir değer döndürür, ancak geçersiz olabilir. Bu nedenle, dönüştürmenin **`reinterpret_cast`** başarılı olacağını bilmiyorsanız kullanmanızın önerilmediğini öneririz. Ayrıca, ile özdeş oldukları için C++/CX kodunuzda C stili yayınları kullanmanızı öneririz **`reinterpret_cast`** .

Derleyici ve çalışma zamanı, bir değer türü veya yerleşik tür bağımsız değişken olarak parametre türü olan bir yönteme geçirildiğinde de örtük yayınlar gerçekleştirir — Örneğin, kutulama işlemleri `Object^` . Teorik olarak, örtük bir dönüştürme çalışma zamanında bir özel duruma asla neden olmaz; derleyici örtük bir dönüştürme gerçekleştiremediğinde, derleme zamanında bir hata oluşturur.

Windows Çalışma Zamanı, özel durumlar yerine HRESULT hata kodları kullanan COM üzerinden soyutlamadır. Genel olarak, [Platform:: InvalidCastException](../cppcx/platform-invalidcastexception-class.md) , E_NOINTERFACE alt düzey bir com hatası olduğunu gösterir.

## <a name="static_cast"></a>static_cast

, **`static_cast`** İki tür arasında bir devralma ilişkisi olup olmadığını anlamak için derleme zamanına göre denetlenir. Türler ilgili değilse, atama derleyici hatasına neden olur.

**`static_cast`** Ref sınıfında bir de çalışma zamanı denetiminin gerçekleştirilmesine neden olur. Bir **`static_cast`** başvuru sınıfındaki a, derleme zamanı doğrulaması geçirebilir ancak hala çalışma zamanında başarısız olur; bu durumda bir `Platform::InvalidCastException` oluşturulur. Genel olarak, neredeyse her zaman geliştirme ve test sırasında ortadan kaldırabildiğiniz programlama hatalarını belirttiğinden, bu özel durumları işlemek zorunda kalmazsınız.

**`static_cast`** Kod iki tür arasında açıkça bir ilişki bildirirse kullanın ve bu nedenle dönüştürmenin çalışması gerekir.

```cpp
    interface class A{};
    public ref class Class1 sealed : A { };
    // ...
    A^ obj = ref new Class1(); // Class1 is an A
    // You know obj is a Class1. The compiler verifies that this is possible, and in C++/CX a run-time check is also performed.
    Class1^ c = static_cast<Class1^>(obj);
```

## <a name="safe_cast"></a>safe_cast

**Safe_cast** işleci Windows çalışma zamanı bir parçasıdır. Çalışma zamanı tür denetimi gerçekleştirir ve dönüştürme başarısız olursa bir oluşturur `Platform::InvalidCastException` . Bir çalışma zamanı hatası olağanüstü bir koşulu gösteriyorsa **safe_cast** kullanın. **Safe_cast** birincil amacı, geliştirme ve test aşamaları sırasında ortaya çıkabilecek bir noktada programlama hatalarının tanımlanmasına yardımcı olur. İşlenmeyen özel durumun kendi hata noktasını tanımladığı için özel durumu işlemek zorunda değilsiniz.

Kod ilişkiyi bildirmiyorsa ancak dönüştürmenin çalışması gerektiği için safe_cast kullanın.

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

Bir **`dynamic_cast`** nesneyi daha fazla türetilmiş bir türe (özellikle de daha özel olarak, bir hat **^** ) aktardığınızda, hedef nesnenin bazen bazı durumlarda **`nullptr`** veya dönüştürmenin başarısız olabileceğinden ya da bu koşulu bir özel durum yerine normal bir kod yolu olarak işlemek istiyorsanız kullanın. Örneğin, **boş uygulama (Evrensel Windows)** proje şablonunda `OnLaunched` app. XAMP. cpp yöntemi **`dynamic_cast`** uygulama penceresinde içerik olup olmadığını test etmek için kullanır. İçerik yoksa bir hata değildir; beklenen bir durumdur. `Windows::Current::Content` , bir `Windows::UI::XAML::UIElement` ve dönüştürme `Windows::UI.XAML::Controls::Frame` , devralma hiyerarşisinde daha fazla türetilmiş bir tür olan öğesine.

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

Başka bir kullanımı **`dynamic_cast`** , bir `Object^` kutulanmış değer türü içerip içermediğini tespit etmek üzere araştırması yapmak için. Bu durumda, bir `dynamic_cast<Platform::Box>` veya ' a kalkışın `dynamic_cast<Platform::IBox>` .

## <a name="dynamic_cast-and-tracking-references-"></a>dynamic_cast ve izleme başvuruları (%)

Bir izleme başvurusuna de uygulayabilirsiniz **`dynamic_cast`** , ancak bu durumda cast **safe_cast** gibi davranır. `Platform::InvalidCastException`Bir izleme başvurusunun değeri olmadığı için hata oluşturur **`nullptr`** .

## <a name="reinterpret_cast"></a>reinterpret_cast

Derleme zamanı denetimi veya çalışma zamanı denetimi gerçekleştirilmediğinden [reinterpret_cast](../cpp/reinterpret-cast-operator.md) kullanmanızı öneririz. En kötü durumda, bir **`reinterpret_cast`** hata programlama hatalarının geliştirme sırasında algılanmamasına ve programınızın davranışında kötü veya çok zararlı hatalara neden olmasına olanak sağlar. Bu nedenle, **`reinterpret_cast`** ilgisiz türler arasında atama yapmanız gereken nadir bir durumda ve dönüştürmenin başarılı olacağını bildiğiniz durumlarda kullanmanızı öneririz. Nadiren kullanılan bir örnek, bir Windows Çalışma Zamanı türünü temel alınan ABı türüne dönüştürmelidir; Yani, nesne için başvuru saymasının denetimini alıyorsunuz. Bunu yapmak için [ComPtr sınıfı](../cpp/com-ptr-t-class.md) akıllı işaretçisini kullanmanızı öneririz. Aksi halde, arabirimde sürümü özel olarak çağırmanız gerekir. Aşağıdaki örnek, bir başvuru sınıfının bir öğesine nasıl yayınlankullanılabileceğini gösterir `IInspectable*` .

```cpp
#include <wrl.h>
using namespace Microsoft::WRL;
auto winRtObject = ref new SomeWinRTType();
ComPtr<IInspectable> inspectable = reinterpret_cast<IInspectable*>(winRtObject);
// ...
```

**`reinterpret_cast`** OneWindows çalışma zamanı arabiriminden diğerine dönüştürmek için kullanırsanız, nesnenin iki kez serbest bırakılması gerekir. Bu nedenle, bu dönüştürmeyi yalnızca C olmayan ve + bileşen uzantıları arabirimine dönüştürürken kullanın.

## <a name="abi-types"></a>ABı türleri

- ABı türler Windows SDK üst bilgilerde canlı. Uygun şekilde, üst bilgiler ad alanlarından sonra adlandırılır — örneğin, `windows.storage.h` .

- ABı türler ABı — Örneğin, özel bir ad alanı içinde canlı `ABI::Windows::Storage::Streams::IBuffer*` .

- Windows Çalışma Zamanı arabirim türü ile eşdeğer ABı türü arasındaki Dönüşümler her zaman güvenlidir — Yani, `IBuffer^` `ABI::IBuffer*` .

- Bir Windows Çalışma Zamanı çalışma zamanı sınıfı `IInspectable*` , biliniyorsa, her zaman varsayılan arabirimine dönüştürülmelidir.

- ABı türlerine dönüştürdükten sonra, türün yaşam süresi ve COM kurallarını izlemeniz gerekir. `WRL::ComPtr`ABI işaretçilerinin ömür yönetimini basitleştirmek için kullanmanızı öneririz.

Aşağıdaki tabloda, kullanımı güvenli olan durumlar özetlenmektedir **`reinterpret_cast`** . Her durumda, her iki yönde de atama güvenlidir.

| Atama, atama | Atama, dönüştürme |
|--|--|
| `HSTRING` | `String^` |
| `HSTRING*` | `String^*` |
| `IInspectable*` | `Object^` |
| `IInspectable**` | `Object^*` |
| `IInspectable-derived-type*` | `same-interface-from-winmd^` |
| `IInspectable-derived-type**` | `same-interface-from-winmd^*` |
| `IDefault-interface-of-RuntimeClass*` | `same-RefClass-from-winmd^` |
| `IDefault-interface-of-RuntimeClass**` | `same-RefClass-from-winmd^*` |

## <a name="see-also"></a>Ayrıca bkz.

- [Tür sistemi](../cppcx/type-system-c-cx.md)
- [C++/CX dil başvurusu](../cppcx/visual-c-language-reference-c-cx.md)
- [Ad alanı başvurusu](../cppcx/namespaces-reference-c-cx.md)
