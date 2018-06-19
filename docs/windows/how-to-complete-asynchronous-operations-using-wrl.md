---
title: 'Nasıl yapılır: WRL kullanarak zaman uyumsuz işlemleri tamamlama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: 02173eae-731b-49bc-b412-f1f69388b99d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fff0a6e98dd6fdd28b1fbc2e9146d5b68975e0f0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33881531"
---
# <a name="how-to-complete-asynchronous-operations-using-wrl"></a>Nasıl Yapılır: WRL Kullanarak Zaman Uyumsuz İşlemleri Tamamlama
Bu belge Windows çalışma zamanı C++ Şablon kitaplığı (WRL) zaman uyumsuz işlemleri başlatmak ve işlemlerini tamamladıktan sonra iş gerçekleştirmek için nasıl kullanılacağını gösterir.  
  
 Bu belge, iki örnek gösterilmektedir. İlk örnek zaman uyumsuz bir süreölçer başlatır ve Zamanlayıcı süresi dolacak şekilde bekler. Zamanlayıcı nesne oluşturduğunuzda, bu örnekte, zaman uyumsuz eylem belirtin. İkinci örnek arka plan iş parçacığı çalıştırır. Bu örnek döndüren bir Windows çalışma zamanı yöntemi ile çalışmaya nasıl gösterir bir `IAsyncInfo` arabirimi. [Geri çağırma](../windows/callback-function-windows-runtime-cpp-template-library.md) işlevi olduğundan örneklerin her ikisi de önemli bir kısmını bunları sonuçlarını zaman uyumsuz işlemlerin işlemek için bir olay işleyicisi belirtmenizi sağlar.  
  
 Bir bileşen örneği oluşturur ve bir özellik değeri alır daha basit bir örnek için bkz [nasıl yapılır: Windows çalışma zamanı bileşenini etkinleştirme ve kullanma](../windows/how-to-activate-and-use-a-windows-runtime-component-using-wrl.md).  
  
> [!TIP]
>  Bu örnekler lambda ifadeleri geri çağırmaları tanımlamak için kullanın. İşlev nesneleri (functors) işlev işaretçileri de kullanabilirsiniz veya [std::function](../standard-library/function-class.md) nesneleri. C++ lambda ifadeleri hakkında daha fazla bilgi için bkz: [Lambda ifadeleri](../cpp/lambda-expressions-in-cpp.md).  
  
## <a name="example-working-with-a-timer"></a>Örnek: bir süreölçer ile çalışma  
 Aşağıdaki adımlarda zaman uyumsuz bir süreölçeri başlatmak ve Zamanlayıcı süresi dolacak şekilde bekleyin. Tam bir örnek aşağıda verilmiştir.  
  
> [!WARNING]
>  Genellikle Windows çalışma zamanı C++ Şablon Kitaplığı'ndaki bir evrensel Windows Platformu (UWP) uygulamasını kullanmasına karşın, bu örnek bir konsol uygulaması çizim için kullanır. Gibi işlevleri `wprintf_s` bir UWP uygulamasını kullanılabilir değil. UWP uygulamasında kullanabileceğiniz işlevleri ve türleri hakkında daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) ve [Win32 ve COM UWP uygulamalar için](/uwp/win32-and-com/win32-and-com-for-uwp-apps).  
  
1.  İçerir (`#include`) Windows çalışma zamanı, Windows çalışma zamanı C++ Şablon kitaplığı ya da C++ Standart Kitaplığı üstbilgilerini gerekli.  
  
     [!code-cpp[wrl-consume-async#2](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_1.cpp)]  
  
     Zaman uyumsuz bir zamanlayıcı kullanmak için gereken türleri Windows.System.Threading.h bildirir.  
  
     Kullanan öneririz `using namespace` .cpp dosyanızdaki kodunu daha okunabilir hale getirmek için yönerge.  
  
2.  Windows çalışma zamanı başlatılamıyor.  
  
     [!code-cpp[wrl-consume-async#3](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_2.cpp)]  
  
3.  İçin etkinleştirme fabrikası oluşturma `ABI::Windows::System::Threading::IThreadPoolTimer` arabirimi.  
  
     [!code-cpp[wrl-consume-async#4](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_3.cpp)]  
  
     Windows çalışma zamanı tam olarak nitelenmiş adlar türlerini tanımlamak için kullanır. `RuntimeClass_Windows_System_Threading_ThreadPoolTimer` Parametredir Windows çalışma zamanı tarafından sağlanan ve gerekli çalışma zamanı sınıf adını içeren bir dize.  
  
4.  Oluşturma bir [olay](../windows/event-class-windows-runtime-cpp-template-library.md) ana uygulama için Zamanlayıcı geri eşitler nesnesi.  
  
     [!code-cpp[wrl-consume-async#5](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_4.cpp)]  
  
    > [!NOTE]
    >  Bu olay, bir konsol uygulaması bir parçası olarak yalnızca tanıtım içindir. Bu örnek olay zaman uyumsuz bir işlem önce uygulama çıkar tamamlandığından emin olmak için kullanır. Çoğu uygulamada Zaman uyumsuz işlemleri için genellikle beklemeyen.  
  
5.  Oluşturma bir `IThreadPoolTimer` iki saniye sonra süresi dolar nesnesi. Kullanım `Callback` olay işleyicisi oluşturmak için işlevi (bir `ABI::Windows::System::Threading::ITimerElapsedHandler` nesnesi).  
  
     [!code-cpp[wrl-consume-async#6](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_5.cpp)]  
  
6.  Bir ileti konsola yazdırma ve Zamanlayıcı geri çağırma tamamlanmasını bekleyin. Tüm `ComPtr` ve RAII nesneleri kapsam bırakın ve otomatik olarak yayımlanmıştır.  
  
     [!code-cpp[wrl-consume-async#7](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_6.cpp)]  
  
 Aşağıda, tam bir örnek verilmiştir:  
  
 [!code-cpp[wrl-consume-async#1](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_7.cpp)]  
  
### <a name="compiling-the-code"></a>Kod Derleniyor  
 Kodu derlemek için kopyalayın ve ardından bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `wrl-consume-async.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe wrl tüketen async.cpp runtimeobject.lib**  
  
## <a name="example-working-with-a-background-thread"></a>Örnek: arka plan iş parçacığı ile çalışma  
 Aşağıdaki adımlar bir çalışan iş parçacığı Başlat ve bu iş parçacığı tarafından gerçekleştirilen eylem tanımlayın. Tam bir örnek aşağıda verilmiştir.  
  
> [!TIP]
>  Bu örnek ile çalışmaya nasıl gösterir `ABI::Windows::Foundation::IAsyncAction` arabirimi. Bu deseni uygulayan herhangi bir arabirimi uygulayabilirsiniz `IAsyncInfo`: `IAsyncAction`, `IAsyncActionWithProgress`, `IAsyncOperation`, ve `IAsyncOperationWithProgress`.  
  
1.  İçerir (`#include`) Windows çalışma zamanı, Windows çalışma zamanı C++ Şablon kitaplığı ya da C++ Standart Kitaplığı üstbilgilerini gerekli.  
  
     [!code-cpp[wrl-consume-asyncOp#2](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_8.cpp)]  
  
     Bir çalışan iş parçacığı kullanmak için gereken türleri Windows.System.Threading.h bildirir.  
  
     Kullanmanızı öneririz `using namespace` .cpp dosyanızdaki kodunu daha okunabilir hale getirmek için yönerge.  
  
2.  Windows çalışma zamanı başlatılamıyor.  
  
     [!code-cpp[wrl-consume-asyncOp#3](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_9.cpp)]  
  
3.  İçin etkinleştirme fabrikası oluşturma `ABI::Windows::System::Threading::IThreadPoolStatics` arabirimi.  
  
     [!code-cpp[wrl-consume-asyncOp#4](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_10.cpp)]  
  
4.  Oluşturma bir [olay](../windows/event-class-windows-runtime-cpp-template-library.md) ana uygulama için çalışan iş parçacığı tamamlanmasından eşitler nesnesi.  
  
     [!code-cpp[wrl-consume-asyncOp#5](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_11.cpp)]  
  
    > [!NOTE]
    >  Bu olay, bir konsol uygulaması bir parçası olarak yalnızca tanıtım içindir. Bu örnek olay zaman uyumsuz bir işlem önce uygulama çıkar tamamlandığından emin olmak için kullanır. Çoğu uygulamada Zaman uyumsuz işlemleri için genellikle beklemeyen.  
  
5.  Çağrı `IThreadPoolStatics::RunAsync` yöntemi bir çalışan iş parçacığı oluşturulamadı. Kullanım `Callback` eylemi tanımlamak için işlev.  
  
     [!code-cpp[wrl-consume-asyncOp#6](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_12.cpp)]  
  
     `IsPrime` İşlevi aşağıdaki tam bir örnek tanımlanır.  
  
6.  Bir ileti konsola yazdırma ve iş parçacığı tamamlanmasını bekleyin. Tüm `ComPtr` ve RAII nesneleri kapsam bırakın ve otomatik olarak yayımlanmıştır.  
  
     [!code-cpp[wrl-consume-asyncOp#7](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_13.cpp)]  
  
 Aşağıda, tam bir örnek verilmiştir:  
  
 [!code-cpp[wrl-consume-asyncOp#1](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_14.cpp)]  
  
### <a name="compiling-the-code"></a>Kod Derleniyor  
 Kodu derlemek için kopyalayın ve ardından bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `wrl-consume-asyncOp.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe wrl tüketen asyncOp.cpp runtimeobject.lib**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows Çalışma Zamanı C++ Şablon Kitaplığı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)
