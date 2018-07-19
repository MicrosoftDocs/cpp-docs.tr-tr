---
title: "Nasıl yapılır: Windows 10 kullanan Windows Masaüstü uygulama SDK'sı | Microsoft Docs"
ms.custom: get-started-article
ms.date: 07/12/2018
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
ms.openlocfilehash: 07cd0d02edc586697e42e4733df478a7ae394e0f
ms.sourcegitcommit: 9ad287c88bdccee2747832659fe50c2e5d682a0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2018
ms.locfileid: "39034786"
---
# <a name="how-to-use-the-windows-10-sdk-in-a-windows-desktop-application"></a>Nasıl yapılır: Windows 10 kullanan Windows Masaüstü uygulama SDK'sı
Visual Studio 2017'de bir Klasik Windows Masaüstü projesi oluşturduğunuzda, bu varsayılan olarak C++ Masaüstü iş yükü yüklendiğinde veya son güncelleştirme, yüklü Windows 10 SDK sürümünü oluşturmak için ayarlanır. Windows SDK'ın bu sürümü Windows 7 ve sonraki sürümlerle uyumludur. Bkz: [Windows üst bilgileri kullanma](/windows/desktop/WinProg/using-the-windows-headers) belirli Windows sürümlerini hedefleme hakkında daha fazla bilgi.

SDK'sının önceki bir sürümü hedeflemek istiyorsanız, açabileceğiniz **proje | Özellikleri** ve Windows SDK sürümü açılan listede kullanılabilir başka bir SDK sürümleri seçin.
  
 Visual Studio 2015 ve Windows 10 SDK'sı ile başlayarak, CRT kitaplığı (ucrtbase) içeren bir evrensel Windows uygulamalarında kullanılmak üzere kabul edilebilir işlevleri ve diğer her şey (vcruntime140) içeren bir tane olmak üzere iki bölüme ayrıldı. Windows 10 SDK'sı birçok C99 işlevleri gibi yeni işlevler içerdiğinden bu işlevleri kullanmak için şu adımları izlemesi gerekir. Bkz: [CRT kitaplık özellikleri](../c-runtime-library/crt-library-features.md).  
  
### <a name="to-target-the-windows-10-sdk"></a>Windows 10 SDK'yı hedeflemek için  
  
1.  Windows 10 SDK'sı yüklü olduğundan emin olun. Windows 10 SDK'sı bir parçası olarak yüklü **C++ ile masaüstü geliştirme** iş yükü. Bağımsız bir sürümü kullanılabilir [Windows 10 için indirmeler ve Araçlar](https://developer.microsoft.com/windows/downloads).

  
2.  Proje düğümü için kısayol menüsünü açın ve **SDK sürümü yeniden hedefle**.  
  
     ![SDK sürümü için hedefi yeniden](../windows/media/retargetingwindowssdk1.PNG "RetargetingWindowsSDK1")  
  
     **Çözüm eylemleri gözden geçirin** iletişim kutusu görüntülenir.  
  
     ![Çözüm eylemlerini gözden](../windows/media/retargetingwindowssdk2.PNG "RetargetingWindowsSDK2")  
  
3.  İçinde **hedef Platform sürümü** açılan listesinde, hedeflemek istediğiniz Windows 10 SDK'sı sürümünü seçin. Değişikliği uygulamak için Tamam düğmesini seçin.  
  
     Bu bağlamda 8.1 backwardly Windows 8, Windows Server 2012, Windows 7, Windows Server 2008 ve Windows Vista ile uyumlu olan Windows SDK'sı sürüm anlamına geldiğini unutmayın.  
  
     Bu adım, başarılı olursa, aşağıdaki metni çıkış penceresinde görüntülenir:  
  
     `Retargeting End: 1 completed, 0 failed, 0 skipped`  
  
4.  Proje özelliklerini açın ve **yapılandırma özellikleri, genel** bölümünde, değerlerini **Windows hedef Platform sürümü**. Buradaki değer değiştirme, aşağıdaki yordamı aynı etkiye sahiptir. Bkz: [genel özellik sayfası (Proje)](../ide/general-property-page-project.md).  
  
     ![Hedef Platform sürümü](../windows/media/retargetingwindowssdk3.PNG "RetargetingWindowsSDK3")  
  
     Bu eylem, üst bilgi dosyaları ve kitaplık dosyaları için yol eklemeyi proje makrolarını değerlerini değiştirir. Ne Proje Özellikleri iletişim kutusunda, Visual C++ dizinleri bölümünde değiştiğini görmek için ekleme dizinleri gibi özelliklerden birini seçin, açılan listeyi açın ve \<Düzenle >. **Ekleme dizinleri** iletişim kutusu görüntülenir.  
  
     ![Dizinleri iletişim kutusu içeren](../windows/media/retargetingwindowssdk4.PNG "RetargetingWindowsSDK4")  
  
     Seçin **makroları >>** düğmesi ve yeni değerleri görmek için Windows SDK'sı makroları makrolar listesini aşağı kaydırın.  
  
     ![Windows SDK'sı makroları](../windows/media/retargetingwindowssdk5.PNG "RetargetingWindowsSDK5")  
  
5.  Diğer projeler için gerektiği şekilde yineleyin ve çözümü yeniden oluşturun.  
  
### <a name="to-target-the-windows-81-sdk"></a>Windows 8.1 SDK'yı hedeflemek için  
  
1.  Proje düğümü için kısayol menüsünü açın ve **SDK sürümü yeniden hedefle**.  
  
2.  Hedef Platform sürümü açılan listede 8.1 seçin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows Masaüstü uygulamaları (Visual C++)](../windows/how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)
