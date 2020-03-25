---
title: 'Nasıl Yapılır: WRL Kullanarak Olayları İşleme'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 1c77543f-7b0c-4a94-93bf-e3225885ed76
ms.openlocfilehash: 0e13212d7cb481bc72a903a31fb170fd1ff8b7ec
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213934"
---
# <a name="how-to-handle-events-using-wrl"></a>Nasıl Yapılır: WRL Kullanarak Olayları İşleme

Bu belgede, bir Windows Çalışma Zamanı nesnesinin olaylarına abone C++ olmak ve olayları işlemek için Windows çalışma zamanı Şablon kitaplığı 'NıN (WRL) nasıl kullanılacağı gösterilmektedir.

Bu bileşenin bir örneğini oluşturan ve bir özellik değeri alan daha basit bir örnek için bkz. [nasıl yapılır: etkinleştirme ve Windows çalışma zamanı bileşeni kullanma](how-to-activate-and-use-a-windows-runtime-component-using-wrl.md).

## <a name="subscribing-to-and-handling-events"></a>Olaylara abone olma ve olayları Işleme

Aşağıdaki adımlar `ABI::Windows::System::Threading::IDeviceWatcher` nesnesini başlatır ve ilerleme durumunu izlemek için olay işleyicilerini kullanır. `IDeviceWatcher` arabirimi cihazları zaman uyumsuz olarak veya arka planda listelemenize ve cihazlar eklendiğinde, kaldırıldığında veya değiştirildiğinde bildirim almanızı sağlar. [Geri çağırma](callback-function-wrl.md) işlevi, arka plan işleminin sonuçlarını işleyen olay işleyicilerini belirtmesini sağladığından bu örneğin önemli bir bölümüdür. Tüm örnek aşağıda verilmiştir.

> [!WARNING]
> Windows Çalışma Zamanı C++ şablon kitaplığını genellikle bir Evrensel Windows platformu uygulamasında kullanmanıza rağmen bu örnek, çizim için bir konsol uygulaması kullanır. `wprintf_s` gibi işlevler Evrensel Windows Platformu bir uygulamadan kullanılamaz. Evrensel Windows Platformu uygulamasında kullanabileceğiniz türler ve işlevler hakkında daha fazla bilgi için bkz. Evrensel Windows Platformu uygulamalar ve [Win32 ve com IÇIN UWP uygulamalarında](/uwp/win32-and-com/win32-and-com-for-uwp-apps) [Desteklenmeyen crt işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) .

1. Gerekli Windows Çalışma Zamanı, Windows Çalışma Zamanı C++ şablon kitaplığı veya C++ standart kitaplık üstbilgilerini dahil edin (`#include`).

   [!code-cpp[wrl-consume-event#2](../codesnippet/CPP/how-to-handle-events-using-wrl_1.cpp)]

   `Windows.Devices.Enumeration.h` cihazları listelemek için gerekli olan türleri bildirir.

   Kodu daha okunabilir hale getirmek için. cpp dosyanızdaki `using namespace` yönergesini kullanmanızı öneririz.

2. Uygulama için yerel değişkenleri bildirin. Bu örnek, daha sonra etkinliklerden aboneliklerini kaldırma olanağı sağlayan, numaralandırılmış cihazların ve kayıt belirteçlerinin sayısını içerir.

   [!code-cpp[wrl-consume-event#7](../codesnippet/CPP/how-to-handle-events-using-wrl_2.cpp)]

3. Windows Çalışma Zamanı başlatın.

   [!code-cpp[wrl-consume-event#3](../codesnippet/CPP/how-to-handle-events-using-wrl_3.cpp)]

4. Numaralandırma işleminin tamamlanmasını ana uygulamayla eşitleyen bir [olay](event-class-wrl.md) nesnesi oluşturun.

   [!code-cpp[wrl-consume-event#4](../codesnippet/CPP/how-to-handle-events-using-wrl_4.cpp)]

   > [!NOTE]
   > Bu olay yalnızca konsol uygulamasının bir parçası olarak tanıtım amaçlıdır. Bu örnek, uygulamanın uygulamadan önce zaman uyumsuz bir işlemin tamamlanmasını sağlamak için olayını kullanır. Çoğu uygulama için genellikle zaman uyumsuz işlemlerin tamamlanmasını beklememeniz gerekmez.

5. `IDeviceWatcher` arabirimi için bir etkinleştirme fabrikası oluşturun.

   [!code-cpp[wrl-consume-event#5](../codesnippet/CPP/how-to-handle-events-using-wrl_5.cpp)]

   Windows Çalışma Zamanı, türleri tanımlamak için tam nitelikli adlar kullanır. `RuntimeClass_Windows_Devices_Enumeration_DeviceInformation` parametresi, Windows Çalışma Zamanı tarafından sunulan ve gerekli çalışma zamanı sınıf adını içeren bir dizedir.

6. `IDeviceWatcher` nesnesini oluşturun.

   [!code-cpp[wrl-consume-event#6](../codesnippet/CPP/how-to-handle-events-using-wrl_6.cpp)]

7. `Added`, `EnumerationCompleted`ve `Stopped` olaylarına abone olmak için `Callback` işlevini kullanın.

   [!code-cpp[wrl-consume-event#8](../codesnippet/CPP/how-to-handle-events-using-wrl_7.cpp)]

   `Added` olay işleyicisi, numaralandırılan cihazların sayısını artırır. On cihaz bulunduğunda numaralandırma işlemini durduruyor.

   `Stopped` olay işleyicisi olay işleyicilerini kaldırır ve tamamlanma olayını ayarlar.

   `EnumerationCompleted` olay işleyicisi Listeleme işlemini durduruyor. On cihazdan az cihaz olması durumunda bu olayı ele aldık.

   > [!TIP]
   > Bu örnek, geri çağırmaları tanımlamak için bir lambda ifadesi kullanır. İşlev nesnelerini (funörler), işlev işaretçilerini veya [std:: Function](../../standard-library/function-class.md) nesnelerini de kullanabilirsiniz. Lambda ifadeleri hakkında daha fazla bilgi için bkz. [lambda ifadeleri](../../cpp/lambda-expressions-in-cpp.md).

8. Numaralandırma sürecini başlatın.

   [!code-cpp[wrl-consume-event#9](../codesnippet/CPP/how-to-handle-events-using-wrl_8.cpp)]

9. Listeleme işleminin tamamlanmasını bekleyin ve ardından bir ileti yazdırın. Tüm `ComPtr` ve OYıı nesneleri kapsamdan kalır ve otomatik olarak serbest bırakılır.

   [!code-cpp[wrl-consume-event#10](../codesnippet/CPP/how-to-handle-events-using-wrl_9.cpp)]

İşte örnek:

[!code-cpp[wrl-consume-event#1](../codesnippet/CPP/how-to-handle-events-using-wrl_10.cpp)]

## <a name="compiling-the-code"></a>Kod Derleniyor

Kodu derlemek için, kopyalayın ve sonra bir Visual Studio projesine yapıştırın veya `wrl-consume-events.cpp` adlı bir dosyaya yapıştırın ve sonra bir **Visual Studio komut istemi** penceresinde aşağıdaki komutu çalıştırın.

`cl.exe wrl-consume-events.cpp runtimeobject.lib`

## <a name="see-also"></a>Ayrıca bkz.

[Windows Çalışma Zamanı C++ Şablon Kitaplığı (WRL)](windows-runtime-cpp-template-library-wrl.md)
