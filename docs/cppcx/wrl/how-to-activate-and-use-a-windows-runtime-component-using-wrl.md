---
title: 'Nasıl yapılır: WRL kullanarak Windows Çalışma Zamanı bileşenini etkinleştirme ve kullanma'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 54828f02-6af3-45d1-b965-d0104442f8d5
ms.openlocfilehash: 59a031968933ab151dc97a8089aff629026f5ea5
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70926071"
---
# <a name="how-to-activate-and-use-a-windows-runtime-component-using-wrl"></a>Nasıl yapılır: WRL kullanarak Windows Çalışma Zamanı bileşenini etkinleştirme ve kullanma

Bu belgede, Windows Çalışma Zamanı başlatmak için Windows Çalışma Zamanı C++ şablon kitaplığı 'NıN (WRL) nasıl kullanılacağı ve bir Windows çalışma zamanı bileşeninin nasıl etkinleştirileceği ve kullanılacağı gösterilmektedir.

Bir bileşeni kullanmak için bileşen tarafından uygulanan türe bir arabirim işaretçisi almanız gerekir. Windows Çalışma Zamanı temel alınan teknolojisi bileşen nesne modeli (COM) olduğundan, türün bir örneğini korumak için COM kurallarını izlemeniz gerekir. Örneğin, türün bellekten ne zaman silineceğini belirleyen *başvuru sayısını* korumanız gerekir.

Windows çalışma zamanı kullanımını basitleştirmek için, Windows çalışma zamanı C++ şablon kitaplığı, otomatik olarak başvuru sayımı gerçekleştiren akıllı işaretçi şablonu olan [ComPtr\<T >](comptr-class.md)sağlar. Bir değişken bildirdiğinizde `ComPtr<`, *arabirim adı* `>` *tanımlayıcısı*belirtin. Bir arabirim üyesine erişmek için, oka üye erişim işlecini (`->`) tanımlayıcıya uygulayın.

> [!IMPORTANT]
> Bir arabirim işlevi çağırdığınızda, her zaman HRESULT dönüş değerini test edin.

## <a name="activating-and-using-a-windows-runtime-component"></a>Windows Çalışma Zamanı bileşenini etkinleştirme ve kullanma

Aşağıdaki adımlar, bir Windows çalışma zamanı `Windows::Foundation::IUriRuntimeClass` bileşeni için etkinleştirme fabrikası oluşturmayı, bu bileşenin bir örneğini oluşturmayı ve bir özellik değerini almayı göstermek için arabirimini kullanır. Ayrıca, Windows Çalışma Zamanı başlatmayı da gösterir. Tüm örnek aşağıda verilmiştir.

> [!IMPORTANT]
> Windows Çalışma Zamanı C++ şablon kitaplığını genellikle bir evrensel WINDOWS platformu (UWP) uygulamasında kullanmanıza rağmen bu örnek, çizim için bir konsol uygulaması kullanır. `wprintf_s` Gibi işlevler UWP uygulamasında kullanılamaz. UWP uygulamasında kullanabileceğiniz türler ve işlevler hakkında daha fazla bilgi için bkz. Evrensel Windows Platformu uygulamalar ve [Win32 ve com IÇIN UWP uygulamalarında](/uwp/win32-and-com/win32-and-com-for-uwp-apps) [Desteklenmeyen crt işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) .

#### <a name="to-activate-and-use-a-windows-runtime-component"></a>Windows Çalışma Zamanı bileşeni etkinleştirmek ve kullanmak için

1. Gerekli Windows çalışma zamanı`#include`, Windows çalışma zamanı C++ şablon kitaplığı veya C++ standart kitaplık üstbilgilerini ekleyin ().

   [!code-cpp[wrl-consume-component#2](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_1.cpp)]

   Kodu daha okunabilir hale getirmek için `using namespace` . cpp dosyanızdaki yönergeyi kullanmanız önerilir.

2. Uygulamanın çalıştırıldığı iş parçacığını başlatın. Her uygulamanın iş parçacığı ve iş parçacığı modelini başlatması gerekir. Bu örnek, Windows Çalışma Zamanı başlatmak için [Microsoft:: WRL:: Wrapper:: RoInitializeWrapper](roinitializewrapper-class.md) sınıfını kullanır ve iş parçacığı modeli olarak [RO_INIT_MULTITHREADED](/windows/win32/api/roapi/ne-roapi-ro_init_type) belirtir. Sınıf, oluşturma `Windows::Foundation::Uninitialize` sırasında ve yok edildiğinde çağrılır. `Windows::Foundation::Initialize` `RoInitializeWrapper`

   [!code-cpp[wrl-consume-component#3](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_2.cpp)]

   İkinci ifadede, [RoInitializeWrapper:: HRESULT](roinitializewrapper-class.md#hresult) işleci çağrısından öğesine `HRESULT` `Windows::Foundation::Initialize`döndürür.

3. `ABI::Windows::Foundation::IUriRuntimeClassFactory` Arabirim için bir *etkinleştirme fabrikası* oluşturun.

   [!code-cpp[wrl-consume-component#4](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_3.cpp)]

   Windows Çalışma Zamanı, türleri tanımlamak için tam nitelikli adlar kullanır. `RuntimeClass_Windows_Foundation_Uri` Parametresi, Windows çalışma zamanı tarafından sunulan ve gerekli çalışma zamanı sınıf adını içeren bir dizedir.

4. URI`"https://www.microsoft.com"`'yi temsil eden bir [Microsoft:: WRL:: Wrapper:: HString](hstring-class.md) değişkenini başlatın.

   [!code-cpp[wrl-consume-component#6](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_4.cpp)]

   Windows Çalışma Zamanı, Windows Çalışma Zamanı kullanacağı bir dize için bellek ayıramazsınız. Bunun yerine Windows Çalışma Zamanı, dizenin bir kopyasını, tuttuğu ve işlemler için kullandığı bir arabellekte oluşturur ve sonra oluşturduğu arabelleğe bir tanıtıcı döndürür.

5. `IUriRuntimeClassFactory::CreateUri` Bir`ABI::Windows::Foundation::IUriRuntimeClass` nesne oluşturmak için Factory metodunu kullanın.

   [!code-cpp[wrl-consume-component#7](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_5.cpp)]

6. Özelliğindeğerini`Domain` almak için `IUriRuntimeClass::get_Domain` yöntemini çağırın.

   [!code-cpp[wrl-consume-component#8](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_6.cpp)]

7. Etki alanı adını konsola yazdırın ve döndürün. Tüm `ComPtr` ve tüm Rat nesneleri kapsamdan kalır ve otomatik olarak serbest bırakılır.

   [!code-cpp[wrl-consume-component#9](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_7.cpp)]

   [Windowsgetstrıngrawbuffer](/windows/win32/api/winstring/nf-winstring-windowsgetstringrawbuffer) IşLEVI, URI dizesinin temeldeki Unicode biçimini alır.

İşte bu örnek:

[!code-cpp[wrl-consume-component#1](../codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_8.cpp)]

## <a name="compiling-the-code"></a>Kod Derleniyor

Kodu derlemek için, kopyalayın ve sonra bir Visual Studio projesine yapıştırın veya adlandırılmış `wrl-consume-component.cpp` bir dosyaya yapıştırın ve sonra bir Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

`cl.exe wrl-consume-component.cpp runtimeobject.lib`

## <a name="see-also"></a>Ayrıca bkz.

[Windows Çalışma Zamanı C++ Şablon Kitaplığı (WRL)](windows-runtime-cpp-template-library-wrl.md)