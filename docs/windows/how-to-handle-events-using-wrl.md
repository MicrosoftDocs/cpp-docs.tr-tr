---
title: "Nasıl yapılır: WRL kullanarak olayları işleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
ms.assetid: 1c77543f-7b0c-4a94-93bf-e3225885ed76
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a3341992ce2b10897fca165a787e568b5e0bc660
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-handle-events-using-wrl"></a>Nasıl Yapılır: WRL Kullanarak Olayları İşleme
Bu belge Windows çalışma zamanı C++ Şablon kitaplığı (WRL) abone olma ve Windows çalışma zamanı nesne olayları işlemek için nasıl kullanılacağını gösterir.  
  
 Bu bileşen örneği oluşturur ve bir özellik değeri alır daha basit bir örnek için bkz [nasıl yapılır: Windows çalışma zamanı bileşenini etkinleştirme ve kullanma](../windows/how-to-activate-and-use-a-windows-runtime-component-using-wrl.md).  
  
## <a name="subscribing-to-and-handling-events"></a>Abone olma ve olayları işleme  
 Aşağıdaki adımlar başlangıç bir `ABI::Windows::System::Threading::IDeviceWatcher` nesne ve olay işleyicileri ilerleme durumunu izlemek için kullanabilirsiniz. `IDeviceWatcher` Arabirimi zaman uyumsuz olarak veya arka planda cihazlar numaralandırır ve aygıtlar eklendiğinde, kaldırıldı veya değiştirildi bildirimi olanak sağlar. [Geri çağırma](../windows/callback-function-windows-runtime-cpp-template-library.md) işlevi olduğundan bu örnek önemli bir kısmını bu arka plan işlemi sonuçlarını işlem olay işleyicileri belirtmenizi sağlar. Tam bir örnek aşağıda verilmiştir.  
  
> [!WARNING]
>  Genellikle bir evrensel Windows platformu uygulamasında Windows çalışma zamanı C++ Şablon kitaplığı kullanmasına karşın, bu örnek bir konsol uygulaması çizim için kullanır. Gibi işlevleri `wprintf_s` bir evrensel Windows platformu uygulamadan kullanılabilir değil. Türler ve evrensel Windows platformu uygulamasında kullanabileceğiniz işlevler hakkında daha fazla bilgi için bkz: [/ZW ile desteklenmeyen CRT işlevleri](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx) ve [Win32 ve COM için Windows mağazası uygulamaları](http://msdn.microsoft.com/library/windows/apps/br205757.aspx).  
  
1.  İçerir (`#include`) Windows çalışma zamanı, Windows çalışma zamanı C++ Şablon kitaplığı ya da C++ Standart Kitaplığı üstbilgilerini gerekli.  
  
     [!code-cpp[wrl-consume-event#2](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_1.cpp)]  
  
     Windows.Devices.Enumeration.h aygıtları numaralandırmak için gereken türleri bildirir.  
  
     Kullanan öneririz `using namespace` .cpp dosyanızdaki kodunu daha okunabilir hale getirmek için yönerge.  
  
2.  Uygulamayı yerel değişkenleri bildirin. Bu örnek sayısını numaralandırılmış aygıtlar ve daha sonra olaylarından aboneliği etkinleştirmek kayıt belirteçleri tutar.  
  
     [!code-cpp[wrl-consume-event#7](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_2.cpp)]  
  
3.  Windows çalışma zamanı başlatılamıyor.  
  
     [!code-cpp[wrl-consume-event#3](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_3.cpp)]  
  
4.  Oluşturma bir [olay](../windows/event-class-windows-runtime-cpp-template-library.md) ana uygulamanın numaralandırma işlemi tamamlandığında eşitler nesnesi.  
  
     [!code-cpp[wrl-consume-event#4](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_4.cpp)]  
  
    > [!NOTE]
    >  Bu olay, bir konsol uygulaması bir parçası olarak yalnızca tanıtım içindir. Bu örnek olay zaman uyumsuz bir işlem önce uygulama çıkar tamamlandığından emin olmak için kullanır. Çoğu uygulamada Zaman uyumsuz işlemleri için genellikle beklemeyen.  
  
5.  İçin etkinleştirme fabrikası oluşturma `IDeviceWatcher` arabirimi.  
  
     [!code-cpp[wrl-consume-event#5](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_5.cpp)]  
  
     Windows çalışma zamanı tam olarak nitelenmiş adlar türlerini tanımlamak için kullanır. `RuntimeClass_Windows_Devices_Enumeration_DeviceInformation` Parametredir Windows çalışma zamanı tarafından sağlanan ve gerekli çalışma zamanı sınıf adını içeren bir dize.  
  
6.  Oluşturma `IDeviceWatcher` nesnesi.  
  
     [!code-cpp[wrl-consume-event#6](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_6.cpp)]  
  
7.  Kullanım `Callback` abone olmak için işlevi `Added`, `EnumerationCompleted`, ve `Stopped` olaylar.  
  
     [!code-cpp[wrl-consume-event#8](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_7.cpp)]  
  
     `Added` Olay işleyicisi numaralandırılmış aygıtların sayısını artırır. On aygıtları bulunamadığında numaralandırma işlemi durdurur.  
  
     `Stopped` Olay işleyicisi olay işleyicileri kaldırır ve tamamlama olayını ayarlar.  
  
     `EnumerationCompleted` Olay işleyicisi numaralandırma işlemi durdurur. 10'dan az aygıtları olasılığına Biz bu olayı işleyin.  
  
    > [!TIP]
    >  Bu örnek bir lambda ifadesi geri çağırmaları tanımlamak için kullanır. İşlev nesneleri (functors) işlev işaretçileri de kullanabilirsiniz veya [std::function](../standard-library/function-class.md) nesneleri. Lambda ifadeleri hakkında daha fazla bilgi için bkz: [Lambda ifadeleri](../cpp/lambda-expressions-in-cpp.md).  
  
8.  Numaralandırma işlemi başlatın.  
  
     [!code-cpp[wrl-consume-event#9](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_8.cpp)]  
  
9. Numaralandırma işlemi tamamlayın ve ardından bir ileti yazdırmak bekleyin. Tüm `ComPtr` ve RAII nesneleri kapsam bırakın ve otomatik olarak yayımlanmıştır.  
  
     [!code-cpp[wrl-consume-event#10](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_9.cpp)]  
  
 Aşağıda, tam bir örnek verilmiştir:  
  
 [!code-cpp[wrl-consume-event#1](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_10.cpp)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Kodu derlemek için kopyalayın ve ardından bir Visual Studio projesi yapıştırın veya adlı bir dosyaya yapıştırın `wrl-consume-events.cpp` ve ardından Visual Studio komut istemi penceresinde aşağıdaki komutu çalıştırın.  
  
 **cl.exe wrl tüketen events.cpp runtimeobject.lib**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows Çalışma Zamanı C++ Şablon Kitaplığı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)