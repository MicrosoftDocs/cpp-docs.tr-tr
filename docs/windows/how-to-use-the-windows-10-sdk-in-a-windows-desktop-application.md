---
title: "Nasıl yapılır: Windows 10 SDK 'Yı bir Windows masaüstü uygulamasında kullanma"
description: Windows 10 SDK 'Yı kullanmak için bir Windows masaüstü uygulaması projesindeki hedef SDK sürümünü ayarlama.
ms.custom: get-started-article
ms.date: 01/22/2020
ms.assetid: eed6421e-9355-44a6-9582-3f1d453a6d44
ms.openlocfilehash: c1d71b591398453f7cee02aa22cd2e377991588f
ms.sourcegitcommit: b67b08472b6f1ee8f1c5684bba7056d3e0fc745f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76725740"
---
# <a name="how-to-use-the-windows-10-sdk-in-a-windows-desktop-application"></a>Nasıl yapılır: Windows 10 SDK 'Yı bir Windows masaüstü uygulamasında kullanma

Visual Studio 'da yeni bir klasik Windows Masaüstü projesi oluşturduğunuzda, varsayılan olarak Windows 10 SDK 'sını hedefler. C++ Masaüstü iş yükünü yüklerken Visual STUDIO Bu SDK 'nın bir sürümünü yükler. Windows 10 SDK, Windows 7 SP1 ve üzeri için kod yazmayı destekler. Belirli Windows sürümlerini hedefleme hakkında daha fazla bilgi için bkz. [Windows üst bilgilerini kullanma](/windows/win32/WinProg/using-the-windows-headers) ve [WINVER ve _WIN32_WINNT güncelleştirme](../porting/modifying-winver-and-win32-winnt.md).

Mevcut bir projeyi yükselttiğinizde, bir seçiminiz vardır: projenizde belirtilen hedef Windows SDK kullanmaya devam edebilirsiniz. Ya da, Windows 10 SDK 'Yı kullanmak için projenizi yeniden hedefleyebilirsiniz. Windows 10 SDK ile en son işletim sistemleri ve dil standartları için desteğin avantajlarından yararlanın.

## <a name="use-the-right-windows-sdk-for-your-project"></a>Projeniz için doğru Windows SDK kullanın

Visual Studio 2015 ile başlayarak, C çalışma zamanı (CRT) kitaplığı iki parçaya ayrılmıştır: bir bölüm, ucrtbase, Evrensel Windows uygulamalarında kullanabileceğiniz standart C ve Microsoft 'a özgü CRT işlevlerini içerir. Bu kitaplık artık Universal CRT veya UCRT olarak bilinir ve Windows 10 SDK 'sına taşınmıştır. UCRT, en son C++ dil standartlarını desteklemek Için gereken C99 işlevleri gibi birçok yeni işlev içerir. Orijinal CRT 'nin diğer bölümü vcruntime ' dır. C çalışma zamanı desteğini, başlatma ve sonlandırma kodunu ve UCRT 'ye gitmediğiniz diğer her şeyi içerir. Vcruntime kitaplığı, Visual Studio 'da C++ derleyici ve araç kümesi ile birlikte yüklenir. Daha fazla bilgi için bkz. [CRT kitaplık özellikleri](../c-runtime-library/crt-library-features.md).

UıCRT artık Windows 10 ' un her sürümünde yüklü olan bir sistem bileşenidir. Windows 'un önceki tüm desteklenen sürümleri için yüklenebilir bir bileşen olarak da kullanılabilir. Windows 'un desteklenen tüm sürümlerini hedeflemek için Windows 10 SDK 'sını kullanabilirsiniz. Desteklenen işletim sistemlerinin tüm listesi için bkz. [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk).

Projelerinizi, Visual Studio 2015 ' den önceki bir proje sürümünden yükselttiğinizde Windows 10 SDK 'sını kullanmak üzere yeniden hedeflemek için aşağıdaki adımları izleyin:

### <a name="to-target-the-windows-10-sdk"></a>Windows 10 SDK 'sını hedeflemek için

1. Windows 10 SDK 'nın yüklü olduğundan emin olun. Windows 10 SDK, iş yüküyle **Masaüstü geliştirmenin C++**  bir parçası olarak yüklenir. [Windows 10 Için indirmeler ve araçlar](https://developer.microsoft.com/windows/downloads)'da tek başına sürüm kullanılabilir.

1. Proje düğümü için kısayol menüsünü açın ve **projeleri yeniden hedefle**' yi seçin. (Visual Studio 'nun önceki sürümlerinde **SDK sürümünü yeniden hedefle**' yi seçin.) **Çözüm eylemlerini gözden geçir** iletişim kutusu görüntülenir.

   ![Çözüm eylemlerini gözden geçirme](../windows/media/retargetingwindowssdk2.PNG "RetargetingWindowsSDK2")

1. **Hedef platform sürümü** açılan listesinde, hedeflemek istediğiniz WINDOWS 10 SDK sürümünü seçin. Genel anlamda, en son yüklenen sürümü seçmenizi öneririz. Değişikliği uygulamak için **Tamam** düğmesini seçin.

   Bu bağlamdaki 8,1 Windows 8.1 SDK 'Sı anlamına gelir.

   Bu adım başarılı olursa, çıkış penceresinde aşağıdaki metin görüntülenir:

   `Retargeting End: 1 completed, 0 failed, 0 skipped`

1. Proje Özellikleri iletişim kutusunu açın. **Yapılandırma özellikleri** > **genel** bölümünde, **Windows hedef platformu sürümü**değerlerine dikkat edin. Burada değeri değiştirmek, bu yordamın takip eden etkile aynı etkiye sahiptir. Daha fazla bilgi için bkz. [genel özellik sayfası (proje)](../build/reference/general-property-page-project.md).

   ![Hedef platform sürümü](../windows/media/retargetingwindowssdk3.PNG "RetargetingWindowsSDK3")

   Bu eylem, üstbilgi dosyalarına ve kitaplık dosyalarına yollar içeren proje makrolarının değerlerini değiştirir. Nelerin değiştiğini görmek için, **Proje özellikleri** Iletişim kutusunun **görsel C++ dizinler** bölümünü açın. **Içerme dizinleri**gibi özelliklerden birini seçin. Sonra, özellik değerinin açılan listesini açın ve **\<düzenle >** ' yi seçin. **Dizinleri dahil et** iletişim kutusu görüntülenir.

   ![Dizinleri dahil et iletişim kutusu](../windows/media/retargetingwindowssdk4.PNG "RetargetingWindowsSDK4")

   **Makrolar > >** düğmesini seçin ve tüm yeni değerleri görmek için makrolar listesini Windows SDK makrolarına kaydırın.

   ![Windows SDK makrolar](../windows/media/retargetingwindowssdk5.PNG "RetargetingWindowsSDK5")

1. Gerektiğinde diğer çözüm projeleri için yeniden hedefleme yordamını tekrarlayın ve çözümü yeniden derleyin.

### <a name="to-target-the-windows-81-sdk"></a>Windows 8.1 SDK 'sını hedeflemek için

1. Çözüm Gezgini ' de proje düğümünün kısayol menüsünü açın ve **projeleri yeniden hedefle**' yi seçin. (Visual Studio 'nun önceki sürümlerinde **SDK sürümünü yeniden hedefle**' yi seçin.)

2. **Hedef platform sürümü** açılan listesinde **8,1**' yi seçin.

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek yol: geleneksel Windows masaüstü uygulaması (C++) oluşturma](../windows/walkthrough-creating-windows-desktop-applications-cpp.md)
