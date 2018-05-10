---
title: "Nasıl yapılır: Windows 10 kullanan Windows masaüstü uygulaması SDK'da | Microsoft Docs"
ms.custom: get-started-article
ms.date: 04/19/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: eed6421e-9355-44a6-9582-3f1d453a6d44
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2dae6f31082176c94cdf12cf0cdb42ba13aa93fe
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="how-to-use-the-windows-10-sdk-in-a-windows-desktop-application"></a>Nasıl yapılır: Windows 10 kullanan Windows masaüstü uygulaması SDK'sına
Visual Studio 2017 içinde Klasik Windows Masaüstü projesi oluşturduğunuzda, onu varsayılan olarak C++ Masaüstü iş yükü yüklendiğinde veya son güncelleştirme yüklediğiniz Windows 10 SDK sürümünü oluşturmak için ayarlanır. Bu Windows SDK'ın tüm son Windows sürümleriyle uyumlu sürümüdür. SDK'ın önceki bir sürümünü hedeflemek istiyorsanız, proje açabilirsiniz | Özellikleri ve Windows SDK sürümü açılır menüde kullanılabilir diğer bir SDK sürümlerini seçin.  
  
 Visual Studio 2015 ve Windows 10 SDK'sı ile başlayarak, CRT kitaplık (ucrtbase) içeren bir evrensel Windows uygulamaları kullanılacak kabul edilebilir işlevleri ve şey (vcruntime140) içeren bir olmak üzere iki bölümden ayrıldı. Windows 10 SDK birçok C99 işlevleri gibi yeni işlevleri içerdiğinden bu işlevleri kullanmak için şu adımları izleyin gerekir. Bkz: [CRT kitaplık özellikleri](../c-runtime-library/crt-library-features.md).  
  
### <a name="to-target-the-windows-10-sdk"></a>Hedef Windows 10 SDK'sı  
  
1.  Windows 10 SDK yüklü olduğundan emin olun. Windows 10 SDK parçası olarak yüklenen **C++ ile masaüstü geliştirme** iş yükü. Bir tek başına sürümünü şu adresten edinilebilir [indirir ve Windows 10 için Araçlar](https://developer.microsoft.com/windows/downloads).

  
2.  Proje düğümünün kısayol menüsünü açın ve seçin **yeniden hedefleyin SDK sürümü**.  
  
     ![SDK sürümü yeniden hedefleyin](../windows/media/retargetingwindowssdk1.PNG "RetargetingWindowsSDK1")  
  
     **Gözden geçirme çözüm Eylemler** iletişim kutusu görüntülenir.  
  
     ![Çözüm eylemleri gözden geçirin](../windows/media/retargetingwindowssdk2.PNG "RetargetingWindowsSDK2")  
  
3.  İçinde **hedef Platform sürümü** açılır listesinde, hedeflediğiniz Windows 10 SDK sürümünü seçin. Değişikliği uygulamak için Tamam düğmesini seçin.  
  
     Bu bağlamda 8.1 de Windows 8, Windows Server 2012, Windows 7, Windows Server 2008 ve Windows Vista ile backwardly uyumlu Windows SDK sürümü anlamına geldiğini unutmayın.  
  
     Bu adım başarılı olursa, aşağıdaki metni çıktı penceresinde görüntülenir:  
  
     `Retargeting End: 1 completed, 0 failed, 0 skipped`  
  
4.  Proje özelliklerini açın ve **yapılandırma özellikleri, genel** bölümünde, değerlerini **Windows hedef Platform sürümü**. Buradaki değer değiştirerek aşağıdaki yordamı aynı etkiye sahiptir. Bkz: [genel özellik sayfası (Proje)](../ide/general-property-page-project.md).  
  
     ![Hedef Platform sürümü](../windows/media/retargetingwindowssdk3.PNG "RetargetingWindowsSDK3")  
  
     Bu eylem üstbilgi dosyaları ve kitaplık dosyaları için yol eklemeyi proje makroları değerlerini değiştirir. Nelerin Proje Özellikleri iletişim kutusunda, Visual C++ dizinleri bölümünde değiştiğini görmek için kapsam dizinleri gibi özelliklerden birini seçin, açılır listeyi açın ve seçin seçebilirsiniz \<Düzenle >. **İçerme dizinleri** iletişim kutusu görüntülenir.  
  
     ![Dizinleri iletişim kutusu içeren](../windows/media/retargetingwindowssdk4.PNG "RetargetingWindowsSDK4")  
  
     Seçin **makroları >>** düğmesi ve tüm yeni değerleri görmek için Windows SDK makroları makrolar listesini aşağı kaydırın.  
  
     ![Windows SDK makroları](../windows/media/retargetingwindowssdk5.PNG "RetargetingWindowsSDK5")  
  
5.  Diğer projeler için gerektiği şekilde yineleyin ve çözümü yeniden derleyin.  
  
### <a name="to-target-the-windows-81-sdk"></a>Hedef Windows 8.1 SDK'sı  
  
1.  Proje düğümünün kısayol menüsünü açın ve seçin **yeniden hedefleyin SDK sürümü**.  
  
2.  Hedef Platform sürümü açılır listede 8.1 seçin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows Masaüstü uygulamaları (Visual C++)](../windows/how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)
