---
title: 'Nasıl yapılır: WRL kullanarak Windows çalışma zamanı bileşenini etkinleştirme ve kullanma'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 54828f02-6af3-45d1-b965-d0104442f8d5
ms.openlocfilehash: 4b8ce40e6c28f952596cab48848873be91b73c95
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54334956"
---
# <a name="how-to-activate-and-use-a-windows-runtime-component-using-wrl"></a>Nasıl yapılır: WRL kullanarak Windows çalışma zamanı bileşenini etkinleştirme ve kullanma

Bu belge, Windows çalışma zamanı'nı başlatmak için Windows çalışma zamanı C++ Şablon kitaplığı (WRL) kullanmayı ve Windows çalışma zamanı bileşenini etkinleştirme ve kullanma işlemini gösterir.

Bir bileşeni kullanmak için bileşen tarafından uygulanan türü bir arabirim işaretçisine edinmeniz gerekir. Ve Windows çalışma zamanı temel teknoloji, Bileşen Nesne Modeli (COM) olduğundan, türün bir örneğini korumak için COM kuralları izlemelidir. Örneğin, korumalıdır *başvuru sayısı* türü bellekten silindiğinde belirler.

Windows çalışma zamanı kullanımını basitleştirmek için akıllı işaretçi şablon, Windows çalışma zamanı C++ Şablon kitaplığı sağlar [ComPtr\<T >](comptr-class.md), bu otomatik başvuru sayımı gerçekleştirir. Bir değişken bildirdiğinizde belirtin `ComPtr<` *arabirim adı* `>` *tanımlayıcı*. Bir arabirim üyesi erişmek için ok üye erişim işleci Uygula (`->`) tanımlayıcı.

> [!IMPORTANT]
> Her zaman bir arabirim işlevini çağırdığınızda, HRESULT dönüş değerini test edin.

## <a name="activating-and-using-a-windows-runtime-component"></a>Etkinleştirme ve bir Windows çalışma zamanı bileşeni kullanma

Aşağıdaki adımları kullanın `Windows::Foundation::IUriRuntimeClass` özellik değerini almak bir etkinleştirme fabrikası bir Windows çalışma zamanı bileşeni oluşturma ve bu bileşen örneği oluşturma işlemini göstermek için arabirim. Bunlar ayrıca, Windows çalışma zamanı başlatma işlemini göstermektedir. Eksiksiz bir örnek aşağıda verilmiştir.

> [!IMPORTANT]
> Genellikle bir evrensel Windows Platformu (UWP) uygulaması Windows çalışma zamanı C++ Şablon kitaplığı kullanırsınız, ancak bu örnek bir konsol uygulaması çizim için kullanılır. Gibi işlevler `wprintf_s` bir UWP uygulaması kullanılabilir değil. Bir UWP uygulamasında kullanabileceğiniz işlevleri ve türleri hakkında daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) ve [Win32 ve COM UWP uygulamaları için](/uwp/win32-and-com/win32-and-com-for-uwp-apps).

#### <a name="to-activate-and-use-a-windows-runtime-component"></a>Bir Windows çalışma zamanı bileşenini etkinleştirme ve kullanma için

1. İçerir (`#include`) Windows çalışma zamanı, Windows çalışma zamanı C++ Şablon kitaplığı ve standart C++ Kitaplığı üstbilgilerini gerekli.

   [!code-cpp[wrl-consume-component#2](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_1.cpp)]

   Öneririz, makineler'den `using namespace` kod daha okunabilir yapmak için .cpp dosyanızdaki yönergesi.

2. İçinde uygulamayı yürüten iş parçacığı başlatın. Her uygulamanın kendi iş parçacığı ve iş parçacığı modeli başlatmanız gerekir. Bu örnekte [Microsoft::WRL::Wrappers::RoInitializeWrapper](roinitializewrapper-class.md) belirtir ve Windows çalışma zamanı'nı başlatmak için sınıf [RO_INIT_MULTITHREADED](https://msdn.microsoft.com/library/windows/apps/br224661.aspx) iş parçacığı modeli olarak. `RoInitializeWrapper` Sınıf çağrıları `Windows::Foundation::Initialize` , yapım sırasında ve `Windows::Foundation::Uninitialize` zaman yok.

   [!code-cpp[wrl-consume-component#3](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_2.cpp)]

   İkinci deyim içinde [RoInitializeWrapper::HRESULT](roinitializewrapper-class.md#hresult) işleci döndürür `HRESULT` çağrısından `Windows::Foundation::Initialize`.

3. Oluşturma bir *etkinleştirme fabrikası* için `ABI::Windows::Foundation::IUriRuntimeClassFactory` arabirimi.

   [!code-cpp[wrl-consume-component#4](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_3.cpp)]

   Windows çalışma zamanı türlerini tanımlamak üzere tam olarak nitelenmiş adlar kullanır. `RuntimeClass_Windows_Foundation_Uri` Parametredir, Windows çalışma zamanı tarafından sağlanan ve gerekli çalışma zamanı sınıf adı içeren bir dize.

4. Başlatma bir [Microsoft::WRL::Wrappers::HString](hstring-class.md) URI temsil eden değişken `"http://www.microsoft.com"`.

   [!code-cpp[wrl-consume-component#6](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_4.cpp)]

   Windows çalışma zamanı'nda Windows çalışma zamanı kullanan bir dize için bellek ayırmayın. Bunun yerine, Windows çalışma zamanı, korur ve işlemleri için kullanır ve ardından, oluşturduğunuz bir tanıtıcı arabelleğe döndürür bir arabellek, dizenin bir kopyasını oluşturur.

5. Kullanım `IUriRuntimeClassFactory::CreateUri` oluşturmak için Üreteç yöntemi bir `ABI::Windows::Foundation::IUriRuntimeClass` nesne.

   [!code-cpp[wrl-consume-component#7](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_5.cpp)]

6. Çağrı `IUriRuntimeClass::get_Domain` değerini almak için yöntemi `Domain` özelliği.

   [!code-cpp[wrl-consume-component#8](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_6.cpp)]

7. Etki alanı adı konsola yazdırma ve döndürür. Tüm `ComPtr` ve RAII nesneleri kapsam bırakın ve otomatik olarak yayımlanır.

   [!code-cpp[wrl-consume-component#9](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_7.cpp)]

   [WindowsGetStringRawBuffer](https://msdn.microsoft.com/library/windows/apps/br224636.aspx) işlevi URI dizesinin temel alınan Unicode biçiminde alır.

Tam bir örnek aşağıda verilmiştir:

[!code-cpp[wrl-consume-component#1](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_8.cpp)]

## <a name="compiling-the-code"></a>Kod Derleniyor

Kodu derlemek için kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `wrl-consume-component.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

`cl.exe wrl-consume-component.cpp runtimeobject.lib`

## <a name="see-also"></a>Ayrıca Bkz.

[Windows Çalışma Zamanı C++ Şablon Kitaplığı (WRL)](windows-runtime-cpp-template-library-wrl.md)