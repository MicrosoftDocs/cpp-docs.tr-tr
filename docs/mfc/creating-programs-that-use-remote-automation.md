---
title: "Uzaktan otomasyon kullanan programlar oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Remote Automation, creating programs
ms.assetid: 8eb31320-1037-4029-b1f3-fdc9406dbaf1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 86a9b9f4dccaaa3a97366dffb11955d3b148aff5
ms.sourcegitcommit: fa7a6dccddce3747389c91277a53e296f905305c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="creating-programs-that-use-remote-automation"></a>Uzaktan Otomasyon Kullanan Programlar Oluşturma
Herhangi bir Otomasyon nesnesi ve herhangi bir Otomasyon denetleyicisi uzaktan Otomasyon kaynak kodu derleme gerek kalmadan ve yeniden bağlama için gerek kalmadan herhangi bir değişiklik olmadan kullanmaya devam edebilir. Yerel olarak çalışan bir ayarladıktan sonra (diğer bir deyişle, aynı makine üzerindeki), uzaktan yürütmek için yalnızca birkaç adımda gitmek.  
  
#### <a name="to-execute-the-remote-automation-object"></a>Uzak Otomasyon nesnesini çalıştırmak için  
  
1.  İstemci makine veya makinelerde uygulamayı kaydedin.  
  
2.  Uzak sunucu kullanmak için istemci erişimi yapılandırın.  
  
3.  Yükleme ve uygulama sunucusu makinede veya makineler kaydedin.  
  
4.  Sunucuyu uzaktan etkinleştirmeye izin verecek şekilde yapılandırın.  
  
5.  Otomasyon Yöneticisi'ni sunucu makineler yükleyin.  
  
6.  Otomasyon Yöneticisi sunuculara çalıştırın.  
  
7.  Uygulamayı, istemci üzerinde çalıştırın.  
  
 Çoğu sunucuları kendini kaydetme olarak 1. adım en kolay yükleme ve sunucu uygulaması istemci makinede yürütülmekte olan tarafından gerçekleştirilir. Kurulum yerel olarak test, önceden bu aşama zaten tamamlandı. Sunucu uygulaması değilse, kendi kendine kayıt, bunu yapmak isteyebilirsiniz. Aksi takdirde, bu adımı gerçekleştirmek için yerel kullanıcı çalıştırabilirsiniz bir kayıt dosyası sağlamanız gerekir. Bunlardan hiçbirine bunu yaparsanız, sizin veya bir yöneticinin kayıt defterini elle düzenlemeniz gerekir en gelişmiş kullanıcılar dışındaki tüm için önerilmez bir yordam.  
  
 Adım 2 Uzaktan Otomasyon bağlantı (RAC) Yöneticisi'ni kullanmayı içerir. RAC Yöneticisi'ni çalıştırın ve sunucu bağlantısı sekmesi üst olduğundan emin olun. Ardından, sunucu nesnesi için girişi bulun **OLE sınıfları** bölmesinde ve onu tıklayın. Ardından **ağ adresi** birleşik giriş kutusu ve uzak yürütülebilir dosya çalıştırılacak sunucusu makine adını girin. Örneğin, girebilirsiniz \\\MyServer burada. Daha sonra uygun ağ protokolü sağlanan listeden seçin. Hangi protokolü önerilen belirlemek için ağ yöneticinize denetlemeniz gerekebilir. Çoğu durumda, bu TCP/IP'yi olacaktır. Son olarak, bir kimlik doğrulama düzeyi seçmek isteyebilirsiniz. Çoğu durumda bu sol (hiçbiri) olarak ya da varsayılan olacaktır. Şimdi sunucuya sağ tıklayın **OLE sınıfları** bölmesi. Bu, yerel veya uzak işlemi seçebileceği bir kısayol menüsü oluşturur. Uzaktan seçin.  
  
 3. adım düzgün yüklenmesi ve seçilen sunucu makinesi veya makinelerde sunucu uygulaması kaydettirilirken içerir. Uygulamanın kendi kendine kayıt ise, yeniden kez yürütme de kaydeder.  
  
 4. adım uzaktan yürütme izin vermek için sunucu yapılandırmayı içerir. RAC Yöneticisi server makinesinde çalıştırabilir ve emin **istemci erişimi** sekmesi odağı vardır. İstediğiniz etkinleştirme modeli seçin (genellikle **anahtarı tarafından uzaktan oluşturur izin**. Bu seçeneği seçerseniz, ayrıca tıklamanız gerekir **uzaktan etkinleştirmeye izin** 'Y' için kayıt defteri girdisinin değeri ayarlamak için onay kutusunu). İzin uzak oluşturur (ACL) seçeneğini seçerseniz, ACL ileterek Düzenle seçeneğine de sahip **Düzenle ACL** düğmesi.  
  
 Çalışmak uzak Otomasyon izin vermek için ardından Otomasyon Yöneticisi yüklü ve çalışan sunucu makinede veya makineleri olduğundan emin olmak gerekir. Yüklenmemişse, AUTMGR32 kopyalayın. EXE Windows Sistem dizini. Bunun nasıl yapılacağı hakkında daha fazla bilgi için bkz: [uzak Otomasyon yüklemesi](../mfc/remote-automation-installation.md). Uzak Otomasyon başlatmak için Otomasyon Yöneticisi'ni yürütün. İleti sayısı gösterileceği küçük durum penceresi görüntülenir. Başlatıldıktan sonra kendisini küçülür. Durum bilgisi görmeye devam etmek istiyorsanız, tıklayabilirsiniz **Otomasyon Yöneticisi** pencereyi geri yüklemek için görev çubuğunda sekme.  
  
 İstemci makinesinde istemci uygulamasını çalıştırmak için son adımdır bakın. Yukarıdaki adımları izlediyseniz, bu sunucu nesnesine bağlanmak ve tam olarak yerel olarak yaptığınız gibi biraz yavaş barındırabilir yürütün.  
  
 RAC Yöneticisi ayrıca, uzak Otomasyonu ve Dağıtılmış COM (DCOM, DCOM destek bu platformları) arasında geçiş yapmak izin verdiğini radyo düğmesi tek bir tıklatmayla dikkat edin. DCOM seçerseniz, çeşitli diğer yapılandırma seçeneklerini ayarlayabilirsiniz. Daha fazla ayrıntı için DCOM belgelerine bakın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzak Otomasyon](../mfc/remote-automation.md)   
 [AUTOCLIK ve AUTODRIV Kullanarak Uzak Otomasyonu Çalıştırma](../mfc/running-remote-automation-using-autoclik-and-autodriv.md)

