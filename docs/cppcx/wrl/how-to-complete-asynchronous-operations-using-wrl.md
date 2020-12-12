---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: WRL kullanarak zaman uyumsuz işlemleri Tamam'
title: 'Nasıl Yapılır: WRL Kullanarak Zaman Uyumsuz İşlemleri Tamamlama'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 02173eae-731b-49bc-b412-f1f69388b99d
ms.openlocfilehash: f8c929d737f113d995b5d171896517b3d94a6aa4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97124598"
---
# <a name="how-to-complete-asynchronous-operations-using-wrl"></a>Nasıl Yapılır: WRL Kullanarak Zaman Uyumsuz İşlemleri Tamamlama

Bu belgede, Windows Çalışma Zamanı C++ Şablon kitaplığı 'nın (WRL), zaman uyumsuz işlemleri başlatmak ve işlemler tamamlandığında iş gerçekleştirmek için nasıl kullanılacağı gösterilmektedir.

Bu belgede iki örnek gösterilmektedir. İlk örnek, zaman uyumsuz bir Zamanlayıcı başlatır ve zamanlayıcının kullanım süresini bekler. Bu örnekte, Zamanlayıcı nesnesini oluştururken zaman uyumsuz eylemi belirtirsiniz. İkinci örnek bir arka plan çalışan iş parçacığı çalıştırır. Bu örnek, bir arabirim döndüren Windows Çalışma Zamanı yöntemiyle nasıl çalışalınacağını gösterir `IAsyncInfo` . [Geri çağırma](callback-function-wrl.md) işlevi, zaman uyumsuz işlemlerin sonuçlarını işlemek üzere bir olay işleyicisi belirtmesini sağladığından, her iki örneğin önemli bir bölümüdür.

Bir bileşenin örneğini oluşturan ve bir özellik değeri alan daha basit bir örnek için bkz. [nasıl yapılır: etkinleştirme ve Windows çalışma zamanı bileşeni kullanma](how-to-activate-and-use-a-windows-runtime-component-using-wrl.md).

> [!TIP]
> Bu örnekler, geri çağırmaları tanımlamak için lambda ifadeleri kullanır. İşlev nesnelerini (funörler), işlev işaretçilerini veya [std:: Function](../../standard-library/function-class.md) nesnelerini de kullanabilirsiniz. C++ lambda ifadeleri hakkında daha fazla bilgi için bkz. [lambda ifadeleri](../../cpp/lambda-expressions-in-cpp.md).

## <a name="example-working-with-a-timer"></a>Örnek: bir zamanlayıcı ile çalışma

Aşağıdaki adımlarda zaman uyumsuz bir Zamanlayıcı başlatılır ve zamanlayıcının kullanım süresini dolacaktır. Tüm örnek aşağıda verilmiştir.

> [!WARNING]
> Genellikle Windows Çalışma Zamanı C++ şablon kitaplığını bir Evrensel Windows Platformu (UWP) uygulamasında kullanmanıza rağmen bu örnek, çizim için bir konsol uygulaması kullanır. Gibi işlevler `wprintf_s` UWP uygulamasında kullanılamaz. UWP uygulamasında kullanabileceğiniz türler ve işlevler hakkında daha fazla bilgi için bkz. Evrensel Windows Platformu uygulamalar ve [Win32 ve com IÇIN UWP uygulamalarında](/uwp/win32-and-com/win32-and-com-for-uwp-apps) [Desteklenmeyen crt işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) .

1. `#include`Gerekli Windows çalışma zamanı, Windows çalışma zamanı C++ Şablon kitaplığı veya C++ standart kitaplığı üst bilgilerini ekleyin ().

   [!code-cpp[wrl-consume-async#2](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_1.cpp)]

   `Windows.System.Threading.h` zaman uyumsuz bir zamanlayıcı kullanmak için gerekli olan türleri bildirir.

   `using namespace`Kodu daha okunabilir hale getirmek için. cpp dosyanızdaki yönergeyi kullanmanız önerilir.

2. Windows Çalışma Zamanı başlatın.

   [!code-cpp[wrl-consume-async#3](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_2.cpp)]

3. Arabirim için bir etkinleştirme fabrikası oluşturun `ABI::Windows::System::Threading::IThreadPoolTimer` .

   [!code-cpp[wrl-consume-async#4](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_3.cpp)]

   Windows Çalışma Zamanı, türleri tanımlamak için tam nitelikli adlar kullanır. `RuntimeClass_Windows_System_Threading_ThreadPoolTimer`Parametresi, Windows çalışma zamanı tarafından sunulan ve gerekli çalışma zamanı sınıf adını içeren bir dizedir.

4. Süreölçer geri aramasını ana uygulamayla eşitleyen bir [olay](event-class-wrl.md) nesnesi oluşturun.

   [!code-cpp[wrl-consume-async#5](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_4.cpp)]

   > [!NOTE]
   > Bu olay yalnızca konsol uygulamasının bir parçası olarak tanıtım amaçlıdır. Bu örnek, uygulamanın uygulamadan önce zaman uyumsuz bir işlemin tamamlanmasını sağlamak için olayını kullanır. Çoğu uygulama için genellikle zaman uyumsuz işlemlerin tamamlanmasını beklememeniz gerekmez.

5. `IThreadPoolTimer`İki saniye sonra süresi dolacak bir nesne oluşturun. `Callback`Olay işleyicisini (bir nesne) oluşturmak için işlevini kullanın `ABI::Windows::System::Threading::ITimerElapsedHandler` .

   [!code-cpp[wrl-consume-async#6](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_5.cpp)]

6. Konsola bir ileti yazdırın ve zamanlayıcı geri çağrısının tamamlanmasını bekleyin. Tüm `ComPtr` ve tüm Rat nesneleri kapsamdan kalır ve otomatik olarak serbest bırakılır.

   [!code-cpp[wrl-consume-async#7](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_6.cpp)]

İşte örnek:

[!code-cpp[wrl-consume-async#1](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_7.cpp)]

### <a name="compiling-the-code"></a>Kod Derleniyor

Kodu derlemek için, kopyalayın ve sonra bir Visual Studio projesine yapıştırın veya adlandırılmış bir dosyaya yapıştırın `wrl-consume-async.cpp` ve sonra bir Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.

`cl.exe wrl-consume-async.cpp runtimeobject.lib`

## <a name="example-working-with-a-background-thread"></a>Örnek: bir arka plan Iş parçacığıyla çalışma

Aşağıdaki adımlar bir çalışan iş parçacığı başlatır ve bu iş parçacığı tarafından gerçekleştirilen eylemi tanımlar. Tüm örnek aşağıda verilmiştir.

> [!TIP]
> Bu örnek, arabirimiyle nasıl çalışabileceğinizi gösterir `ABI::Windows::Foundation::IAsyncAction` . Bu kalıbı `IAsyncInfo` : `IAsyncAction` , `IAsyncActionWithProgress` , `IAsyncOperation` ve uygulayan tüm arayüze uygulayabilirsiniz `IAsyncOperationWithProgress` .

1. `#include`Gerekli Windows çalışma zamanı, Windows çalışma zamanı C++ Şablon kitaplığı veya C++ standart kitaplığı üst bilgilerini ekleyin ().

   [!code-cpp[wrl-consume-asyncOp#2](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_8.cpp)]

   Windows.SysTem. Threading. h, bir çalışan iş parçacığını kullanmak için gerekli olan türleri bildirir.

   `using namespace`Kodu daha okunabilir hale getirmek için. cpp dosyanızda yönergesini kullanmanızı öneririz.

2. Windows Çalışma Zamanı başlatın.

   [!code-cpp[wrl-consume-asyncOp#3](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_9.cpp)]

3. Arabirim için bir etkinleştirme fabrikası oluşturun `ABI::Windows::System::Threading::IThreadPoolStatics` .

   [!code-cpp[wrl-consume-asyncOp#4](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_10.cpp)]

4. Çalışan iş parçacığının tamamlanmasını ana uygulamaya eşitleyen bir [olay](event-class-wrl.md) nesnesi oluşturun.

   [!code-cpp[wrl-consume-asyncOp#5](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_11.cpp)]

   > [!NOTE]
   > Bu olay yalnızca konsol uygulamasının bir parçası olarak tanıtım amaçlıdır. Bu örnek, uygulamanın uygulamadan önce zaman uyumsuz bir işlemin tamamlanmasını sağlamak için olayını kullanır. Çoğu uygulama için genellikle zaman uyumsuz işlemlerin tamamlanmasını beklememeniz gerekmez.

5. `IThreadPoolStatics::RunAsync`Bir çalışan iş parçacığı oluşturmak için yöntemini çağırın. `Callback`Eylemi tanımlamak için işlevini kullanın.

   [!code-cpp[wrl-consume-asyncOp#6](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_12.cpp)]

   `IsPrime`İşlev, aşağıdaki örnek olarak tanımlanır.

6. Konsola bir ileti yazdırın ve iş parçacığının tamamlanmasını bekleyin. Tüm `ComPtr` ve tüm Rat nesneleri kapsamdan kalır ve otomatik olarak serbest bırakılır.

   [!code-cpp[wrl-consume-asyncOp#7](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_13.cpp)]

İşte örnek:

[!code-cpp[wrl-consume-asyncOp#1](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_14.cpp)]

### <a name="compiling-the-code"></a>Kod Derleniyor

Kodu derlemek için, kopyalayın ve sonra bir Visual Studio projesine yapıştırın veya adlandırılmış bir dosyaya yapıştırın `wrl-consume-asyncOp.cpp` ve sonra bir **Visual Studio komut istemi** penceresinde aşağıdaki komutu çalıştırın.

`cl.exe wrl-consume-asyncOp.cpp runtimeobject.lib`

## <a name="see-also"></a>Ayrıca bkz.

[Windows Çalışma Zamanı C++ Şablon Kitaplığı (WRL)](windows-runtime-cpp-template-library-wrl.md)
