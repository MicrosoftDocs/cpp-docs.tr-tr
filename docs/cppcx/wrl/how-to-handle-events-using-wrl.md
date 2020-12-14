---
description: 'Daha fazla bilgi edinin: nasıl yapılır: WRL kullanarak olayları Işleme'
title: 'Nasıl Yapılır: WRL Kullanarak Olayları İşleme'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 1c77543f-7b0c-4a94-93bf-e3225885ed76
ms.openlocfilehash: b1be04c1356594e2dc2060d031f35d836ad277bb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229190"
---
# <a name="how-to-handle-events-using-wrl"></a>Nasıl Yapılır: WRL Kullanarak Olayları İşleme

Bu belgede, bir Windows Çalışma Zamanı nesnesinin olaylarına abone olmak ve olayları işlemek için Windows Çalışma Zamanı C++ Şablon kitaplığı 'nın (WRL) nasıl kullanılacağı gösterilmektedir.

Bu bileşenin bir örneğini oluşturan ve bir özellik değeri alan daha basit bir örnek için bkz. [nasıl yapılır: etkinleştirme ve Windows çalışma zamanı bileşeni kullanma](how-to-activate-and-use-a-windows-runtime-component-using-wrl.md).

## <a name="subscribing-to-and-handling-events"></a>Olaylara abone olma ve olayları Işleme

Aşağıdaki adımlar, bir `ABI::Windows::System::Threading::IDeviceWatcher` nesnesi başlatır ve ilerlemeyi izlemek için olay işleyicilerini kullanır. `IDeviceWatcher`Arabirim, cihazları zaman uyumsuz olarak veya arka planda listelemenize ve cihazlar eklendiğinde, kaldırıldığında veya değiştirildiğinde bildirim almanızı sağlar. [Geri çağırma](callback-function-wrl.md) işlevi, arka plan işleminin sonuçlarını işleyen olay işleyicilerini belirtmesini sağladığından bu örneğin önemli bir bölümüdür. Tüm örnek aşağıda verilmiştir.

> [!WARNING]
> Windows Çalışma Zamanı C++ şablon kitaplığını genellikle bir Evrensel Windows Platformu uygulamasında kullanmanıza rağmen bu örnek, çizim için bir konsol uygulaması kullanır. Gibi işlevler `wprintf_s` Evrensel Windows platformu bir uygulamadan kullanılamaz. Evrensel Windows Platformu uygulamasında kullanabileceğiniz türler ve işlevler hakkında daha fazla bilgi için bkz. Evrensel Windows Platformu uygulamalar ve [Win32 ve com IÇIN UWP uygulamalarında](/uwp/win32-and-com/win32-and-com-for-uwp-apps) [Desteklenmeyen crt işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) .

1. `#include`Gerekli Windows çalışma zamanı, Windows çalışma zamanı C++ Şablon kitaplığı veya C++ standart kitaplığı üst bilgilerini ekleyin ().

   [!code-cpp[wrl-consume-event#2](../codesnippet/CPP/how-to-handle-events-using-wrl_1.cpp)]

   `Windows.Devices.Enumeration.h` cihazları listelemek için gerekli olan türleri bildirir.

   `using namespace`Kodu daha okunabilir hale getirmek için. cpp dosyanızdaki yönergeyi kullanmanız önerilir.

2. Uygulama için yerel değişkenleri bildirin. Bu örnek, daha sonra etkinliklerden aboneliklerini kaldırma olanağı sağlayan, numaralandırılmış cihazların ve kayıt belirteçlerinin sayısını içerir.

   [!code-cpp[wrl-consume-event#7](../codesnippet/CPP/how-to-handle-events-using-wrl_2.cpp)]

3. Windows Çalışma Zamanı başlatın.

   [!code-cpp[wrl-consume-event#3](../codesnippet/CPP/how-to-handle-events-using-wrl_3.cpp)]

4. Numaralandırma işleminin tamamlanmasını ana uygulamayla eşitleyen bir [olay](event-class-wrl.md) nesnesi oluşturun.

   [!code-cpp[wrl-consume-event#4](../codesnippet/CPP/how-to-handle-events-using-wrl_4.cpp)]

   > [!NOTE]
   > Bu olay yalnızca konsol uygulamasının bir parçası olarak tanıtım amaçlıdır. Bu örnek, uygulamanın uygulamadan önce zaman uyumsuz bir işlemin tamamlanmasını sağlamak için olayını kullanır. Çoğu uygulama için genellikle zaman uyumsuz işlemlerin tamamlanmasını beklememeniz gerekmez.

5. Arabirim için bir etkinleştirme fabrikası oluşturun `IDeviceWatcher` .

   [!code-cpp[wrl-consume-event#5](../codesnippet/CPP/how-to-handle-events-using-wrl_5.cpp)]

   Windows Çalışma Zamanı, türleri tanımlamak için tam nitelikli adlar kullanır. `RuntimeClass_Windows_Devices_Enumeration_DeviceInformation`Parametresi, Windows çalışma zamanı tarafından sunulan ve gerekli çalışma zamanı sınıf adını içeren bir dizedir.

6. Nesnesini oluşturun `IDeviceWatcher` .

   [!code-cpp[wrl-consume-event#6](../codesnippet/CPP/how-to-handle-events-using-wrl_6.cpp)]

7. `Callback` `Added` , Ve olaylarına abone olmak için işlevini kullanın `EnumerationCompleted` `Stopped` .

   [!code-cpp[wrl-consume-event#8](../codesnippet/CPP/how-to-handle-events-using-wrl_7.cpp)]

   `Added`Olay işleyicisi, numaralandırılan cihazların sayısını artırır. On cihaz bulunduğunda numaralandırma işlemini durduruyor.

   `Stopped`Olay işleyicisi olay işleyicilerini kaldırır ve tamamlanma olayını ayarlar.

   `EnumerationCompleted`Olay işleyicisi, numaralandırma işlemini durduruyor. On cihazdan az cihaz olması durumunda bu olayı ele aldık.

   > [!TIP]
   > Bu örnek, geri çağırmaları tanımlamak için bir lambda ifadesi kullanır. İşlev nesnelerini (funörler), işlev işaretçilerini veya [std:: Function](../../standard-library/function-class.md) nesnelerini de kullanabilirsiniz. Lambda ifadeleri hakkında daha fazla bilgi için bkz. [lambda ifadeleri](../../cpp/lambda-expressions-in-cpp.md).

8. Numaralandırma sürecini başlatın.

   [!code-cpp[wrl-consume-event#9](../codesnippet/CPP/how-to-handle-events-using-wrl_8.cpp)]

9. Listeleme işleminin tamamlanmasını bekleyin ve ardından bir ileti yazdırın. Tüm `ComPtr` ve tüm Rat nesneleri kapsamdan kalır ve otomatik olarak serbest bırakılır.

   [!code-cpp[wrl-consume-event#10](../codesnippet/CPP/how-to-handle-events-using-wrl_9.cpp)]

İşte örnek:

[!code-cpp[wrl-consume-event#1](../codesnippet/CPP/how-to-handle-events-using-wrl_10.cpp)]

## <a name="compiling-the-code"></a>Kod Derleniyor

Kodu derlemek için, kopyalayın ve sonra bir Visual Studio projesine yapıştırın veya adlandırılmış bir dosyaya yapıştırın `wrl-consume-events.cpp` ve sonra bir **Visual Studio komut istemi** penceresinde aşağıdaki komutu çalıştırın.

`cl.exe wrl-consume-events.cpp runtimeobject.lib`

## <a name="see-also"></a>Ayrıca bkz.

[Windows Çalışma Zamanı C++ Şablon Kitaplığı (WRL)](windows-runtime-cpp-template-library-wrl.md)
