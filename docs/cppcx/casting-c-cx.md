---
title: Atama (C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 06/19/2018
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 5247f6c7-6a0a-4021-97c9-21c868bd9455
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 66c0e6bc9d987c400c709e74586e6e37ccc0b715
ms.sourcegitcommit: 301bb19056e5bae84ff50f7d1df1e546efe225ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/21/2018
ms.locfileid: "36306001"
---
# <a name="casting-ccx"></a>Atama (C + +/ CX)

Dört farklı atama işleçleri uygulamak için Windows çalışma zamanı türleri: [static_cast işleci](../cpp/static-cast-operator.md), [dynamic_cast işleci](../cpp/dynamic-cast-operator.md), **safe_cast işleci**, ve [ reinterpret_cast işleci](../cpp/reinterpret-cast-operator.md). **safe_cast** ve **static_cast** dönüştürme gerçekleştirilemediğinde; bir özel durum [static_cast işleci](../cpp/static-cast-operator.md) ayrıca derleme zamanı tür denetimi gerçekleştirir. **dynamic_cast** döndürür **nullptr** türü dönüştürme işlemi başarısız olursa. Ancak **reinterpret_cast** boş olmayan bir değer döndürür geçersiz olabilir. Bu nedenle, değil kullanmanızı öneririz **reinterpret_cast** dönüştürme başarılı olur bilmiyorsanız. Ayrıca, C türü Atamalar, C + kullanmamanızı öneririz +/ CX kod özdeş olduğundan **reinterpret_cast**.

Derleyici ve çalışma zamanı örtük atamalar da gerçekleştirmek — Örneğin, bir değer veya yerleşik türü geçirildiğinde bağımsız değişken olarak bir yöntem parametresi işlemleri kutulama türüdür `Object^`. Örtük bir dönüştürme işlemi, teorik olarak hiçbir zaman bu çalışma zamanında bir özel durum neden olmalıdır; Derleyici örtük bir dönüştürme gerçekleştirilemiyor, derleme sırasında bir hata oluşturur.

Windows çalışma zamanı özel durumları yerine HRESULT hata kodlarını kullanır COM bir Özet biter. Genel olarak, [Platform::InvalidCastException](../cppcx/platform-invalidcastexception-class.md) bir alt düzey E_NOINTERFACE COM hata gösterir.

## <a name="staticcast"></a>static_cast

A **static_cast** iki türleri arasında bir devralma ilişkisi olup olmadığını belirlemek için derleme zamanında denetlenir. Türleri birbiriyle ilgili olmayan, cast derleyici hatası neden olur.

A **static_cast** başvuru üzerinde sınıfı ayrıca bir çalışma zamanı denetimi gerçekleştirilecek neden olur. A **static_cast** bir başvuru üzerinde sınıfı derleme zamanı doğrulama geçirmek ancak hala başarısız çalışma zamanında; bu durumda bir `Platform::InvalidCastException` oluşturulur. Genel olarak, neredeyse her zaman geliştirme ve sınama sırasında çıkarabilirsiniz programlama hataları belirttiğinden, bu özel durumları işleme gerekmez.

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

**Safe_cast** işleci Windows çalışma zamanı bir parçasıdır. Bir çalışma zamanı tür denetimi gerçekleştirir ve oluşturur bir `Platform::InvalidCastException` dönüştürme başarısız olursa. Kullanım **safe_cast** zaman bir çalışma zamanı hatası gösterdiği olağanüstü bir koşul. Birincil amacı **safe_cast** geliştirme sırasında programlama hataları belirlemenize yardımcı olur ve sonuçları ortaya çıktıkları noktada aşamaları test etme. İşlenmeyen özel hata noktası tanımladığından özel durumu işlemek gerekmez.

Safe_cast kodu ilişki bildirmiyor ancak cast çalışmalıdır eminseniz kullanın.

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

Kullanım **dynamic_cast** cast ne zaman bir nesne (daha açık belirtmek gerekirse bir hat **^**) fazla türetilmiş bir tür için iki, hedef beklediğiniz nesne bazen olabilir **nullptr** veya dönüştürme başarısız olabilir ve bu koşulun normal kod yolu yerine bir özel durum olarak işlemek istiyorsanız. Örneğin, **boş uygulama (Evrensel Windows)** proje şablonu, `OnLaunched` app.xamp.cpp kullanır yönteminde **dynamic_cast** uygulaması penceresini içerik olup olmadığını sınamak için. İçerik yoksa, bir hata değildir; Bu beklenen bir durumdur. `Windows::Current::Content` olan bir `Windows::UI::XAML::UIElement` ve dönüştürme için bir `Windows::UI.XAML::Controls::Frame`, devralma hiyerarşisinde daha türetilmiş bir tür değil.

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

Başka bir kullanımını **dynamic_cast** araştırma için bir `Object^` paketlenmiş değer türü içerip içermediğini belirlemek için. Bu durumda, dener bir `dynamic_cast<Platform::Box>` veya `dynamic_cast<Platform::IBox>`.

## <a name="dynamiccast-and-tracking-references-"></a>dynamic_cast ve izleme başvuruları (%)

Aynı zamanda uygulanabilir bir **dynamic_cast** izleme başvurusu, ancak bu durumda dönüştürme gibi davranır **safe_cast**. Bunu oluşturur `Platform::InvalidCastException` hatasında izleme başvurusu değeri olduğundan **nullptr**.

## <a name="reinterpretcast"></a>reinterpret_cast

Değil kullanmanızı öneririz [reinterpret_cast](../cpp/reinterpret-cast-operator.md) bir derleme zamanı denetimi ne bir çalışma zamanı denetimi yapıldığından. En kötü durumda, bir **reinterpret_cast** programlama geliştirme anında algılanmayan gidip programınızın davranışını Zarif veya yıkıcı hata neden hatalarını mümkün kılar. Bu nedenle, kullanmanızı öneririz **reinterpret_cast** ilgisiz türleri arasında dönüştürme ve Dönüştürme başarılı olur bildiğiniz yalnızca bu nadir durumlarda. Windows çalışma zamanı türü, temel alınan ABI türüne dönüştürmek için nadir bir kullanım örneği olan — bu nesne için sayım başvuru denetimin kaplayan anlamına gelir. Bunu yapmak için kullanmanız önerilir [ComPtr sınıfı](../cpp/com-ptr-t-class.md) akıllı işaretçi. Aksi takdirde, özellikle yayın arabirimde çağırmanız gerekir. Aşağıdaki örnek, bir başvuru sınıf nasıl atanabilecek gösterir bir `IInspectable*`.

```cpp
#include <wrl.h>
using namespace Microsoft::WRL;
auto winRtObject = ref new SomeWinRTType();
ComPtr<IInspectable> inspectable = reinterpret_cast<IInspectable*>(winRtObject);
// ...
```

Kullanırsanız **reinterpret_cast** oneWindows çalışma zamanı arabiriminden diğerine dönüştürmek için iki kez yayımlanacak nesnesi neden. Bu nedenle, olmayan bir dönüştürürken yalnızca bu atama kullanın[!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] arabirimi.

## <a name="abi-types"></a>ABI türleri

- ABI türleri Windows SDK üstbilgilerindeki Canlı. Üstbilgileri sonra ad alanlarını uygun şekilde, adlandırılır — Örneğin, `windows.storage.h`.

- ABI türleri canlı bir özel ad ABI — Örneğin, `ABI::Windows::Storage::Streams::IBuffer*`.

- Windows çalışma zamanı arabirim türü ve eşdeğer ABI türü arasında dönüştürme güvenli her zaman — diğer bir deyişle, `IBuffer^` için `ABI::IBuffer*`.

- Windows Çalışma Zamanı Modülü çalışma zamanı sınıf her zaman için dönüştürülüp dönüştürülmeyeceğini `IInspectable*` veya, biliniyorsa, varsayılan arabirimi.

- ABI türlerine dönüştürdükten sonra türü ömrü kendi ve COM kurallara uymalıdır. Kullanmanızı öneririz `WRL::ComPtr` ABI işaretçileri ömür yönetimini basitleştirmek için.

Aşağıdaki tabloda özetlenmiştir olduğu güvenli durumları **reinterpret_cast**. Her durumda dönüştürme her iki yönde de güvenlidir.

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
