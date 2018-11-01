---
title: 'Nasıl Yapılır: WRL Kullanarak Zaman Uyumsuz İşlemleri Tamamlama'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 02173eae-731b-49bc-b412-f1f69388b99d
ms.openlocfilehash: ec57d6dd94357a65b7aaa300d5622ec5feac9932
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50534075"
---
# <a name="how-to-complete-asynchronous-operations-using-wrl"></a>Nasıl Yapılır: WRL Kullanarak Zaman Uyumsuz İşlemleri Tamamlama

Bu belge, Windows çalışma zamanı C++ Şablon kitaplığı (WRL) zaman uyumsuz işlemler başlatmak ve işlemler tamamlandığında iş gerçekleştirmek için nasıl kullanılacağını gösterir.

Bu belge, iki örnek gösterir. İlk örnek, zaman uyumsuz bir süreölçer başlatır ve Zamanlayıcı süresi dolacak şekilde bekler. Zamanlayıcı nesne oluşturduğunuzda, bu örnekte, zaman uyumsuz eylem belirtin. İkinci örnek, bir arka plan iş parçacığı çalıştırır. Bu örnek döndüren bir Windows çalışma zamanı yöntemi ile çalışmaya nasıl gösterir bir `IAsyncInfo` arabirimi. [Geri çağırma](../windows/callback-function-windows-runtime-cpp-template-library.md) işlev örneklerin her ikisi de önemli bir parçası, çünkü bunları zaman uyumsuz işlemlerin sonuçları işlemek için bir olay işleyicisi belirtmenizi sağlar.

Bir bileşenin bir örneğini oluşturur ve bir özellik değeri alan daha temel bir örnek için bkz [nasıl yapılır: bir Windows çalışma zamanı bileşenini etkinleştirme ve kullanma](../windows/how-to-activate-and-use-a-windows-runtime-component-using-wrl.md).

> [!TIP]
> Bu örnekler, lambda ifadeleri geri çağırmaları tanımlamak için kullanın. İşlev nesneleri (işlev nesneleri), işlev işaretçileri de kullanabilirsiniz veya [std::function](../standard-library/function-class.md) nesneleri. C++ lambda ifadeleri hakkında daha fazla bilgi için bkz. [Lambda ifadeleri](../cpp/lambda-expressions-in-cpp.md).

## <a name="example-working-with-a-timer"></a>Örnek: bir Zamanlayıcı ile çalışma

Aşağıdaki adımlar, bir zaman uyumsuz zamanlayıcıyı başlatmak ve Zamanlayıcı sona bekleyin. Eksiksiz bir örnek aşağıda verilmiştir.

> [!WARNING]
> Genellikle bir evrensel Windows Platformu (UWP) uygulaması Windows çalışma zamanı C++ Şablon kitaplığı kullanırsınız, ancak bu örnek bir konsol uygulaması çizim için kullanılır. Gibi işlevler `wprintf_s` bir UWP uygulaması kullanılabilir değil. Bir UWP uygulamasında kullanabileceğiniz işlevleri ve türleri hakkında daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) ve [Win32 ve COM UWP uygulamaları için](/uwp/win32-and-com/win32-and-com-for-uwp-apps).

1. İçerir (`#include`) Windows çalışma zamanı, Windows çalışma zamanı C++ Şablon kitaplığı ve standart C++ Kitaplığı üstbilgilerini gerekli.

   [!code-cpp[wrl-consume-async#2](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_1.cpp)]

   `Windows.System.Threading.h` zaman uyumsuz bir zamanlayıcı kullanmak için gerekli türleri bildirir.

   Öneririz, makineler'den `using namespace` kod daha okunabilir yapmak için .cpp dosyanızdaki yönergesi.

2. Windows çalışma zamanı başlatılamıyor.

   [!code-cpp[wrl-consume-async#3](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_2.cpp)]

3. Bir etkinleştirme fabrikası için oluşturma `ABI::Windows::System::Threading::IThreadPoolTimer` arabirimi.

   [!code-cpp[wrl-consume-async#4](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_3.cpp)]

   Windows çalışma zamanı türlerini tanımlamak üzere tam olarak nitelenmiş adlar kullanır. `RuntimeClass_Windows_System_Threading_ThreadPoolTimer` Parametredir, Windows çalışma zamanı tarafından sağlanan ve gerekli çalışma zamanı sınıf adı içeren bir dize.

4. Oluşturma bir [olay](../windows/event-class-windows-runtime-cpp-template-library.md) nesnesini ana uygulama için Zamanlayıcı geri eşitler.

   [!code-cpp[wrl-consume-async#5](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_4.cpp)]

   > [!NOTE]
   > Bu olay, bir konsol uygulaması bir parçası olarak yalnızca tanıtım içindir. Bu örnek, olayın zaman uyumsuz bir işlemi uygulama çıkışından önce tamamlanmasını sağlamak için kullanır. Çoğu uygulamada genellikle zaman uyumsuz işlemleri için beklemeyin.

5. Oluşturma bir `IThreadPoolTimer` nesnesini iki saniye sonra süresi dolar. Kullanım `Callback` olay işleyicisi oluşturmak için işlevi (bir `ABI::Windows::System::Threading::ITimerElapsedHandler` nesne).

   [!code-cpp[wrl-consume-async#6](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_5.cpp)]

6. Konsoluna bir ileti Yazdır ve Zamanlayıcı geri çağırma tamamlanmasını bekleyin. Tüm `ComPtr` ve RAII nesneleri kapsam bırakın ve otomatik olarak yayımlanır.

   [!code-cpp[wrl-consume-async#7](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_6.cpp)]

Tam bir örnek aşağıda verilmiştir:

[!code-cpp[wrl-consume-async#1](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_7.cpp)]

### <a name="compiling-the-code"></a>Kod Derleniyor

Kodu derlemek için kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `wrl-consume-async.cpp` ve Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

`cl.exe wrl-consume-async.cpp runtimeobject.lib`

## <a name="example-working-with-a-background-thread"></a>Örnek: bir arka plan iş parçacığı ile çalışma

Aşağıdaki adımlar, bir çalışan iş parçacığı ve iş parçacığı tarafından gerçekleştirilen bir eylem tanımlayın. Eksiksiz bir örnek aşağıda verilmiştir.

> [!TIP]
> Bu örnek ile nasıl çalışılacağını gösterir `ABI::Windows::Foundation::IAsyncAction` arabirimi. Bu düzen uygulayan herhangi bir arabirimde uygulayabilirsiniz `IAsyncInfo`: `IAsyncAction`, `IAsyncActionWithProgress`, `IAsyncOperation`, ve `IAsyncOperationWithProgress`.

1. İçerir (`#include`) Windows çalışma zamanı, Windows çalışma zamanı C++ Şablon kitaplığı ve standart C++ Kitaplığı üstbilgilerini gerekli.

   [!code-cpp[wrl-consume-asyncOp#2](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_8.cpp)]

   İş parçacığı kullanmak için gerekli türleri Windows.System.Threading.h bildirir.

   Kullanmanızı öneririz `using namespace` kod daha okunabilir yapmak için .cpp dosyanızdaki yönergesi.

2. Windows çalışma zamanı başlatılamıyor.

   [!code-cpp[wrl-consume-asyncOp#3](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_9.cpp)]

3. Bir etkinleştirme fabrikası için oluşturma `ABI::Windows::System::Threading::IThreadPoolStatics` arabirimi.

   [!code-cpp[wrl-consume-asyncOp#4](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_10.cpp)]

4. Oluşturma bir [olay](../windows/event-class-windows-runtime-cpp-template-library.md) ana uygulama iş parçacığı tamamlanmasından eşitler nesne.

   [!code-cpp[wrl-consume-asyncOp#5](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_11.cpp)]

   > [!NOTE]
   > Bu olay, bir konsol uygulaması bir parçası olarak yalnızca tanıtım içindir. Bu örnek, olayın zaman uyumsuz bir işlemi uygulama çıkışından önce tamamlanmasını sağlamak için kullanır. Çoğu uygulamada genellikle zaman uyumsuz işlemleri için beklemeyin.

5. Çağrı `IThreadPoolStatics::RunAsync` çalışan iş parçacığı oluşturmak için yöntemi. Kullanım `Callback` eylemi tanımlamak için işlevi.

   [!code-cpp[wrl-consume-asyncOp#6](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_12.cpp)]

   `IsPrime` İşlevi izleyen tam bir örnek tanımlanır.

6. Konsoluna bir ileti Yazdır ve tamamlamak iş parçacığı için bekleyin. Tüm `ComPtr` ve RAII nesneleri kapsam bırakın ve otomatik olarak yayımlanır.

   [!code-cpp[wrl-consume-asyncOp#7](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_13.cpp)]

Tam bir örnek aşağıda verilmiştir:

[!code-cpp[wrl-consume-asyncOp#1](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_14.cpp)]

### <a name="compiling-the-code"></a>Kod Derleniyor

Kodu derlemek için kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `wrl-consume-asyncOp.cpp` ve ardından aşağıdaki komutu çalıştırın bir **Visual Studio komut istemi** penceresi.

`cl.exe wrl-consume-asyncOp.cpp runtimeobject.lib`

## <a name="see-also"></a>Ayrıca Bkz.

[Windows Çalışma Zamanı C++ Şablon Kitaplığı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)