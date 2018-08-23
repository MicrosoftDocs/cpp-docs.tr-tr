---
title: Atama (C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 06/19/2018
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 5247f6c7-6a0a-4021-97c9-21c868bd9455
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ea0ac57b178baed76e6ccb7418c778c1ba2306f4
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42613308"
---
# <a name="casting-ccx"></a>Atama (C + +/ CX)

Dört farklı atama işleçleri, Windows çalışma zamanı türleri için geçerlidir: [static_cast işleci](../cpp/static-cast-operator.md), [dynamic_cast işleci](../cpp/dynamic-cast-operator.md), **safe_cast işleci**, ve [ reinterpret_cast işleci](../cpp/reinterpret-cast-operator.md). **safe_cast** ve **static_cast** dönüştürme gerçekleştirilemediğinde; bir özel durum [static_cast işleci](../cpp/static-cast-operator.md) de derleme zamanı tür denetimi gerçekleştirir. **dynamic_cast** döndürür **nullptr** türüne dönüştürme başarısız olursa. Ancak **reinterpret_cast** boş olmayan bir değer döndürür geçersiz olabilir. Bu nedenle, değil kullanmanızı öneririz **reinterpret_cast** atama başarılı olduğunu bilmiyorsanız. Ayrıca, C stili atamaları, C +'da kullanmamanızı öneririz +/ CX kod aynı olduklarından **reinterpret_cast**.

Derleyici ve çalışma zamanı ayrıca örtük atamalar gerçekleştirmek — Örneğin, bir yöntem parametresi bağımsız değişken olarak bir değer türü veya yerleşik tür geçirilir, işlemleri kutulama türüdür `Object^`. Teorik olarak bir örtük tür dönüştürme hiçbir zaman çalışma zamanında bir özel durum neden olmaz; Derleyici örtük bir dönüştürme gerçekleştirilemiyor, derleme sırasında bir hata oluşturur.

Windows çalışma zamanı özel durumları yerine HRESULT hata kodları kullanan COM bir Özet biter. Genel olarak, [Platform::InvalidCastException](../cppcx/platform-invalidcastexception-class.md) e_noınterface bir alt düzey COM hata gösterir.

## <a name="staticcast"></a>static_cast

A **static_cast** iki tür arasında devralma ilişkisi olup olmadığını belirlemek için derleme zamanında denetlenir. Atama türleri birbiriyle ilgili olmayan bir derleyici hatasına neden olur.

A **static_cast** başvuru üzerinde sınıfı da bir çalışma zamanı denetimi gerçekleştirilecek neden olur. A **static_cast** başvuru üzerinde sınıfı derleme zamanı doğrulama başarılı ancak yine de başarısız çalışma zamanında; bu durumda bir `Platform::InvalidCastException` oluşturulur. Genel olarak, neredeyse her zaman geliştirme ve test sırasında ortadan kaldırabilir programlama hatalarını belirttiğinden, bu özel durumları işlemek zorunda değilsiniz.

Kullanım **static_cast** kod iki tür arasında bir ilişki açıkça bildirir ve bu nedenle emin cast çalışması gerekir.

```cpp
    interface class A{};
    public ref class Class1 sealed : A { };
    // ...
    A^ obj = ref new Class1(); // Class1 is an A
    // You know obj is a Class1. The compiler verifies that this is possible, and in C++/CX a run-time check is also performed.
    Class1^ c = static_cast<Class1^>(obj);
```

## <a name="safecast"></a>safe_cast

**Safe_cast** işleci Windows çalışma zamanı'nın bir parçasıdır. Bir çalışma zamanı tür denetimi gerçekleştirir ve oluşturur bir `Platform::InvalidCastException` dönüştürme başarısız olursa. Kullanım **safe_cast** ne zaman bir olağanüstü durum çalışma zamanı hata gösterir. Birincil amacı **safe_cast** geliştirme sırasında programlama hataları belirlemenize yardımcı olur ve sonuçları ortaya çıktıkları noktada aşamaları test. İşlenmeyen özel hata noktasını tanımladığından işlemesi gerekmez.

Kod ilişki bildirmiyor ancak cast çalışmalıdır emin safe_cast kullanın.

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

## <a name="dynamiccast"></a>dynamic_cast

Kullanım **dynamic_cast** cast ne zaman bir nesne (daha açık belirtmek gerekirse bir hat **^**) daha türetilmiş bir tür için ya da, hedef beklediğiniz nesne bazen olabilir **nullptr** veya dönüştürme başarısız olabilir ve bu koşul, bir normal kod yolu yerine bir özel durum olarak işlemek istediğiniz. Örneğin, **boş uygulama (Evrensel Windows)** proje şablonu, `OnLaunched` app.xamp.cpp kullandığı yönteminde **dynamic_cast** uygulama penceresinin içeriği olup olmadığını sınamak için. İçerik yoksa, bir hata değildir; Bu beklenen bir durumdur. `Windows::Current::Content` olan bir `Windows::UI::XAML::UIElement` ve dönüştürme bir `Windows::UI.XAML::Controls::Frame`, devralma hiyerarşisinde daha türetilmiş türü.

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

Başka bir kullanımını **dynamic_cast** araştırma için bir `Object^` paketlenmiş değer türü içerip içermediğini belirlemek için. Bu durumda, denemeden bir `dynamic_cast<Platform::Box>` veya `dynamic_cast<Platform::IBox>`.

## <a name="dynamiccast-and-tracking-references-"></a>dynamic_cast ve izleme başvuruları (%)

Ayrıca uygulama bir **dynamic_cast** izleme başvurusu, ancak bu durumda, tür dönüştürme gibi davranır **safe_cast**. Atar `Platform::InvalidCastException` hatasında bir değeri bir izleme başvurusu olamaz çünkü **nullptr**.

## <a name="reinterpretcast"></a>reinterpret_cast

Değil kullanmanızı öneririz [reinterpret_cast](../cpp/reinterpret-cast-operator.md) çünkü bir derleme zamanı denetimi ya da bir çalışma zamanı denetimi gerçekleştirilir. En kötü durumda, bir **reinterpret_cast** programlama hatalarını geliştirme zamanında algılanmayan gidip, programın davranışını ince veya yıkıcı hatalara neden mümkün kılar. Bu nedenle, kullanmanızı öneririz **reinterpret_cast** ilgisiz türleri arasında dönüştürme gerekir ve atama başarılı olduğunu biliyorsanız, yalnızca bu nadir durumlarda. Bir Windows çalışma zamanı türü, temel alınan ABI türüne dönüştürmek için nadir kullanım örneği olan — bu başvuru sayma nesne için denetimin sürüp anlamına gelir. Bunu yapmak için kullanmanızı öneririz [ComPtr sınıfı](../cpp/com-ptr-t-class.md) akıllı işaretçi. Aksi takdirde, arabirimde özellikle sürüm çağırmanız gerekir. Aşağıdaki örnek, bir başvuru sınıfının nasıl atanabilecek gösterir. bir `IInspectable*`.

```cpp
#include <wrl.h>
using namespace Microsoft::WRL;
auto winRtObject = ref new SomeWinRTType();
ComPtr<IInspectable> inspectable = reinterpret_cast<IInspectable*>(winRtObject);
// ...
```

Kullanırsanız **reinterpret_cast** oneWindows çalışma zamanı arabiriminden diğerine dönüştürmek için nesnenin iki kez serbest bırakılması neden olur. Bu nedenle, olmayan - Visual C++ bileşen uzantıları arabirimine dönüştürülürken yalnızca bu tür dönüştürme kullanın.

## <a name="abi-types"></a>ABI türleri

- Windows SDK'sı üstbilgilerinde Canlı ABI türleri. Üstbilgileri sonra ad alanlarını uygun şekilde, adlandırılır — Örneğin, `windows.storage.h`.

- ABI türlerine özel bir isim uzayında ABI Canlı — Örneğin, `ABI::Windows::Storage::Streams::IBuffer*`.

- Bir Windows çalışma zamanı arabirimi tür ve eşdeğer ABI türü arasında dönüştürme güvenli her zaman — diğer bir deyişle, `IBuffer^` için `ABI::IBuffer*`.

- Bir Windows Çalışma Zamanı Modülü çalışma zamanı sınıf her zaman değerine dönüştürülüp `IInspectable*` veya biliniyorsa, kendi varsayılan arabirim.

- ABI türlerine dönüştürdükten sonra kendi türü ömrünü ve COM kurallara uymanız gerekir. Kullanmanızı öneririz `WRL::ComPtr` ABI işaretçiler ömrü yönetimini kolaylaştırmak için.

Aşağıdaki tabloda özetlenmiştir olduğu kullanmak üzere güvenli çalışmaları **reinterpret_cast**. Her durumda, her iki yönde de cast güvenlidir.

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
- [Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)
- [Ad alanları başvurusu](../cppcx/namespaces-reference-c-cx.md)
