---
title: 'Nasıl yapılır: WRL kullanarak olayları işleme'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 1c77543f-7b0c-4a94-93bf-e3225885ed76
ms.openlocfilehash: 959a85d6cf6de666ae56d09035acefe9a3828ae8
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59033183"
---
# <a name="how-to-handle-events-using-wrl"></a>Nasıl yapılır: WRL kullanarak olayları işleme

Bu belge, Windows çalışma zamanı C++ Şablon kitaplığı (WRL) abone olup bir Windows çalışma zamanı nesnesi olaylarını işlemek için nasıl kullanılacağını gösterir.

Bu bileşenin bir örneğini oluşturur ve bir özellik değeri alan daha temel bir örnek için bkz [nasıl yapılır: Bir Windows çalışma zamanı bileşenini etkinleştirme ve kullanma](how-to-activate-and-use-a-windows-runtime-component-using-wrl.md).

## <a name="subscribing-to-and-handling-events"></a>Abone olma ve olayları işleme

Aşağıdaki adımlar başlangıç bir `ABI::Windows::System::Threading::IDeviceWatcher` nesne ve olay işleyicilerini ilerleme durumunu izlemek için kullanın. `IDeviceWatcher` Arabirimi zaman uyumsuz olarak veya arka plan cihazları listeleme ve aygıtlar eklendiğinde, kaldırıldı veya değiştirildi, bildirim almak etkinleştirir. [Geri çağırma](callback-function-wrl.md) , arka plan işlemi sonuçlarını işleyen olay işleyicileri belirtmek sağladığından işlev, bu örnekte önemli bir parçası. Eksiksiz bir örnek aşağıda verilmiştir.

> [!WARNING]
> Genellikle bir evrensel Windows platformu uygulaması içinde Windows çalışma zamanı C++ Şablon kitaplığı kullanırsınız, ancak bu örnek bir konsol uygulaması çizim için kullanılır. Gibi işlevler `wprintf_s` bir evrensel Windows platformu uygulaması kullanılabilir değil. Bir evrensel Windows platformu uygulamasında kullanabileceğiniz işlevleri ve türleri hakkında daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) ve [Win32 ve COM UWP uygulamaları için](/uwp/win32-and-com/win32-and-com-for-uwp-apps).

1. İçerir (`#include`) Windows çalışma zamanı, Windows çalışma zamanı C++ Şablon kitaplığı ve standart C++ Kitaplığı üstbilgilerini gerekli.

   [!code-cpp[wrl-consume-event#2](../codesnippet/CPP/how-to-handle-events-using-wrl_1.cpp)]

   `Windows.Devices.Enumeration.h` cihazları listelemek için gerekli türleri bildirir.

   Öneririz, makineler'den `using namespace` kod daha okunabilir yapmak için .cpp dosyanızdaki yönergesi.

2. Uygulama için yerel değişkenleri bildirin. Bu örnek, bir dizi numaralandırılmış cihaz ve daha sonra olaylarından aboneliği etkinleştirmek kayıt belirteçleri sayısını tutar.

   [!code-cpp[wrl-consume-event#7](../codesnippet/CPP/how-to-handle-events-using-wrl_2.cpp)]

3. Windows çalışma zamanı başlatılamıyor.

   [!code-cpp[wrl-consume-event#3](../codesnippet/CPP/how-to-handle-events-using-wrl_3.cpp)]

4. Oluşturma bir [olay](event-class-wrl.md) ana uygulamasında numaralandırma işlemi tamamlandığında eşitler nesne.

   [!code-cpp[wrl-consume-event#4](../codesnippet/CPP/how-to-handle-events-using-wrl_4.cpp)]

   > [!NOTE]
   > Bu olay, bir konsol uygulaması bir parçası olarak yalnızca tanıtım içindir. Bu örnek, olayın zaman uyumsuz bir işlemi uygulama çıkışından önce tamamlanmasını sağlamak için kullanır. Çoğu uygulamada genellikle zaman uyumsuz işlemleri için beklemeyin.

5. Bir etkinleştirme fabrikası için oluşturma `IDeviceWatcher` arabirimi.

   [!code-cpp[wrl-consume-event#5](../codesnippet/CPP/how-to-handle-events-using-wrl_5.cpp)]

   Windows çalışma zamanı türlerini tanımlamak üzere tam olarak nitelenmiş adlar kullanır. `RuntimeClass_Windows_Devices_Enumeration_DeviceInformation` Parametredir, Windows çalışma zamanı tarafından sağlanan ve gerekli çalışma zamanı sınıf adı içeren bir dize.

6. Oluşturma `IDeviceWatcher` nesne.

   [!code-cpp[wrl-consume-event#6](../codesnippet/CPP/how-to-handle-events-using-wrl_6.cpp)]

7. Kullanım `Callback` abone olmak için işlev `Added`, `EnumerationCompleted`, ve `Stopped` olayları.

   [!code-cpp[wrl-consume-event#8](../codesnippet/CPP/how-to-handle-events-using-wrl_7.cpp)]

   `Added` Olay işleyicisi numaralandırılmış cihaz sayısını artırır. On cihazınız bulunamadığında numaralandırma işlemi durdurur.

   `Stopped` Olay işleyicisi, olay işleyicilerini kaldırır ve tamamlama olayını ayarlar.

   `EnumerationCompleted` Olay işleyicisi numaralandırma işlemi durdurur. 10'dan az cihazları olasılığına Biz bu olayı işleyin.

   > [!TIP]
   > Bu örnek, geri çağırmaları tanımlamak için bir lambda ifadesi kullanır. İşlev nesneleri (işlev nesneleri), işlev işaretçileri de kullanabilirsiniz veya [std::function](../../standard-library/function-class.md) nesneleri. Lambda ifadeleri hakkında daha fazla bilgi için bkz. [Lambda ifadeleri](../../cpp/lambda-expressions-in-cpp.md).

8. Numaralandırma işlemi başlatın.

   [!code-cpp[wrl-consume-event#9](../codesnippet/CPP/how-to-handle-events-using-wrl_8.cpp)]

9. Numaralandırma işlemi tamamlayın ve ardından iletiyi yazdırmak bekleyin. Tüm `ComPtr` ve RAII nesneleri kapsam bırakın ve otomatik olarak yayımlanır.

   [!code-cpp[wrl-consume-event#10](../codesnippet/CPP/how-to-handle-events-using-wrl_9.cpp)]

Tam bir örnek aşağıda verilmiştir:

[!code-cpp[wrl-consume-event#1](../codesnippet/CPP/how-to-handle-events-using-wrl_10.cpp)]

## <a name="compiling-the-code"></a>Kod Derleniyor

Kodu derlemek için kopyalayın ve bir Visual Studio projesine yapıştırın veya adlı bir dosyaya yapıştırın `wrl-consume-events.cpp` ve ardından aşağıdaki komutu çalıştırın bir **Visual Studio komut istemi** penceresi.

`cl.exe wrl-consume-events.cpp runtimeobject.lib`

## <a name="see-also"></a>Ayrıca bkz.

[Windows Çalışma Zamanı C++ Şablon Kitaplığı (WRL)](windows-runtime-cpp-template-library-wrl.md)