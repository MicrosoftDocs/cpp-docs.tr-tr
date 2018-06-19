---
title: 'Nasıl yapılır: WRL kullanarak Windows çalışma zamanı bileşenini etkinleştirme ve kullanma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: 54828f02-6af3-45d1-b965-d0104442f8d5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 50c37438bf3a840f57119245b845d0b94f1873db
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33880783"
---
# <a name="how-to-activate-and-use-a-windows-runtime-component-using-wrl"></a>Nasıl yapılır: WRL Kullanarak Windows Çalışma Zamanı Bileşenini Etkinleştirme ve Kullanma
Bu belge, Windows çalışma zamanı C++ Şablon kitaplığı (WRL) Windows çalışma zamanı başlatmak için nasıl kullanılacağı ve bir Windows çalışma zamanı bileşenini etkinleştirme ve kullanma nasıl gösterir.  
  
 Bir bileşen kullanmak için bir arabirim işaretçisi bileşen tarafından uygulanan türe edinmeniz gerekir. Ve Windows çalışma zamanı temel alınan teknoloji Bileşen Nesne Modeli (COM) olduğundan, türünün bir örneğini korumak için COM kurallara uymalıdır. Örneğin, tutmalıdır *başvuru sayısı* türü bellekten silindiğinde belirler.  
  
 Windows çalışma zamanı kullanımını kolaylaştırmak için Windows çalışma zamanı C++ Şablon kitaplığı akıllı işaretçi şablonu sağlar [ComPtr\<T >](../windows/comptr-class.md), başvuru sayımı, otomatik olarak gerçekleştirir. Bir değişken bildirirken belirtin `ComPtr<` *arabirim adı* `>` *tanımlayıcısı*. Arabirim üyesini erişmek için ok üye erişimi işleci Uygula (`->`) tanımlayıcı.  
  
> [!IMPORTANT]
>  Bir arabirim işlevi çağırdığınızda, her zaman test `HRESULT` dönüş değeri.  
  
## <a name="activating-and-using-a-windows-runtime-component"></a>Etkinleştirme ve Windows çalışma zamanı bileşeni kullanma  
 Aşağıdaki adımları kullanın `Windows::Foundation::IUriRuntimeClass` etkinleştirme Fabrika Windows çalışma zamanı bileşeni oluşturma, bu bileşen örneği oluşturun ve özellik değeri göstermek için arabirim. Bunlar ayrıca Windows çalışma zamanı başlatılamıyor gösterilmektedir. Tam bir örnek aşağıda verilmiştir.  
  
> [!IMPORTANT]
>  Genellikle Windows çalışma zamanı C++ Şablon Kitaplığı'ndaki bir evrensel Windows Platformu (UWP) uygulamasını kullanmasına karşın, bu örnek bir konsol uygulaması çizim için kullanır. Gibi işlevleri `wprintf_s` bir UWP uygulamasını kullanılabilir değil. UWP uygulamasında kullanabileceğiniz işlevleri ve türleri hakkında daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) ve [Win32 ve COM UWP uygulamalar için](/uwp/win32-and-com/win32-and-com-for-uwp-apps).  
  
#### <a name="to-activate-and-use-a-windows-runtime-component"></a>Windows çalışma zamanı bileşenini etkinleştirme ve kullanma için  
  
1.  İçerir (`#include`) Windows çalışma zamanı, Windows çalışma zamanı C++ Şablon kitaplığı ya da C++ Standart Kitaplığı üstbilgilerini gerekli.  
  
     [!code-cpp[wrl-consume-component#2](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_1.cpp)]  
  
     Kullanan öneririz `using namespace` .cpp dosyanızdaki kodunu daha okunabilir hale getirmek için yönerge.  
  
2.  İçinde uygulama yürüten iş parçacığı başlatılamadı. Her uygulamanın kendi iş parçacığı ve iş parçacığı modelini başlatması gerekir. Bu örnekte [Microsoft::WRL::Wrappers::RoInitializeWrapper](../windows/roinitializewrapper-class.md) belirtir ve Windows çalışma zamanı başlatmak için sınıf [RO_INIT_MULTITHREADED](http://msdn.microsoft.com/library/windows/apps/br224661.aspx) iş parçacığı modeli olarak. `RoInitializeWrapper` Sınıfı çağrıları `Windows::Foundation::Initialize` yapım, adresindeki ve `Windows::Foundation::Uninitialize` zaman yok.  
  
     [!code-cpp[wrl-consume-component#3](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_2.cpp)]  
  
     İkinci deyiminde [RoInitializeWrapper::HRESULT](../windows/roinitializewrapper-hresult-parens-operator.md) operatörü döndürür `HRESULT` çağrıya `Windows::Foundation::Initialize`.  
  
3.  Oluşturma bir *etkinleştirme Fabrika* için `ABI::Windows::Foundation::IUriRuntimeClassFactory` arabirimi.  
  
     [!code-cpp[wrl-consume-component#4](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_3.cpp)]  
  
     Windows çalışma zamanı tam olarak nitelenmiş adlar türlerini tanımlamak için kullanır. `RuntimeClass_Windows_Foundation_Uri` Parametredir Windows çalışma zamanı tarafından sağlanan ve gerekli çalışma zamanı sınıf adını içeren bir dize.  
  
4.  Başlatma bir [Microsoft::WRL::Wrappers::HString](../windows/hstring-class.md) URI temsil eden değişken `"http://www.microsoft.com"`.  
  
     [!code-cpp[wrl-consume-component#6](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_4.cpp)]  
  
     Windows çalışma zamanı'nda Windows çalışma zamanı kullanacağı bir dize için bellek tahsis yok. Bunun yerine, Windows çalışma zamanı, korur ve işlemleri için kullanır ve ardından, oluşturduğunuz bir işleyici arabelleğe döner arabellekte dizenizi bir kopyasını oluşturur.  
  
5.  Kullanım `IUriRuntimeClassFactory::CreateUri` oluşturmak için Üreteç yöntemi bir `ABI::Windows::Foundation::IUriRuntimeClass` nesnesi.  
  
     [!code-cpp[wrl-consume-component#7](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_5.cpp)]  
  
6.  Çağrı `IUriRuntimeClass::get_Domain` değerini almak için yöntemini `Domain` özelliği.  
  
     [!code-cpp[wrl-consume-component#8](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_6.cpp)]  
  
7.  Etki alanı adı konsola yazdırma ve döndürür. Tüm `ComPtr` ve RAII nesneleri kapsam bırakın ve otomatik olarak yayımlanmıştır.  
  
     [!code-cpp[wrl-consume-component#9](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_7.cpp)]  
  
     [WindowsGetStringRawBuffer](http://msdn.microsoft.com/library/windows/apps/br224636.aspx) işlevi URI dizesinin temel Unicode biçiminde alır.  
  
 Aşağıda, tam bir örnek verilmiştir:  
  
 [!code-cpp[wrl-consume-component#1](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_8.cpp)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Kodu derlemek için kopyalayın ve ardından bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `wrl-consume-component.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe wrl tüketen component.cpp runtimeobject.lib**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows Çalışma Zamanı C++ Şablon Kitaplığı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)