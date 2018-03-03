---
title: "UNIX'ten Win32'ye taşıma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- APIs [C++], porting to Win32
- Windows API [C++], migrating from UNIX
- migration [C++]
- UNIX [C++], porting to Win32
- porting to Win32 [C++], from UNIX
- porting to Win32 [C++]
- Win32 applications [C++], migrating from UNIX
ms.assetid: 3837e4fe-3f96-4f24-b2a1-7be94718a881
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b10ee9e9b5a53d6f9f936c4bc158db8ebfb6be13
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
---
# <a name="porting-from-unix-to-win32"></a>UNIX'ten Win32'ye Bağlantı Noktası Oluşturma
Uygulamaları Windows UNIX içinden geçiş için birkaç seçeneğiniz vardır:  
  
-   UNIX'ten Win32 bağlantı noktası uygulamaları için UNIX kitaplıklarını kullanma  
  
-   Uygulamaları UNIX'ten Win32 yerel bağlantı noktası oluşturma  
  
-   POSIX alt sistemini kullanarak UNIX uygulamalar Windows üzerinde çalışan  
  
## <a name="unix-libraries"></a>UNIX kitaplıkları  
 Bir seçenek UNIX programcıları normal olarak dikkate kendi UNIX kod derleme Win32 yürütülebilir izin vermek için üçüncü taraf UNIX benzeri kitaplıkları kullanıyor. Çeşitli ticari (ve en az bir ortak etki alanı) kitaplıklar bunu. Bazı uygulamalar için bir seçenek budur. Bu kitaplıklar taşıma avantajı, bunlar ilk taşıma çabasını en aza olmasıdır. Rekabet yazılım ürünü için ana olumsuz bir uygulamanın yerel bir Win32 bağlantı noktası genellikle daha hızlı olacaktır ve daha fazla işlevsellik kaçınılmaz olarak gerekir ' dir. Daha fazla güç Windows'dan almak için Win32 çağrıları yapması gerektiğinde UNIX kabuğunun dışında adım uygulamanın garip olabilir.  
  
 Aşağıdaki liste, Microsoft ve üçüncü taraf kaynakları taşıma ve UNIX geçiş Visual C++ için destek sağlar:  
  
### <a name="unix-migration-guides"></a>UNIX geçiş kılavuzları  
 UNIX özel uygulama Geçiş Kılavuzu Teknik Yardım kod geçiş UNIX'ten Win32 ortamı sağlar.  
  
 [http://go.microsoft.com/fwlink/p/?linkid=95428](http://go.microsoft.com/fwlink/p/?linkid=95428)  
  
 Unix geçişi Proje Kılavuzu üst düzey Yardım geçirme önemli projeleri UNIX'ten Win32'ye sağlayarak UNIX özel uygulama geçiş kılavuzunu tamamlar. Kılavuzu her proje geçiş aşamasında dikkate alınacak konular öneriler sağlar. Kılavuzu indirilmesi:  
  
 [http://go.microsoft.com/fwlink/p/?linkid=20012](http://go.microsoft.com/fwlink/p/?linkid=20012)  
  
### <a name="microsoft-windows-services-for-unix-sfu"></a>Microsoft Windows Services for UNIX (SFU)  
 Microsoft Windows Services for UNIX (SFU) eksiksiz bir Windows varolan UNIX tabanlı ortamlarla bütünleştirmek için platformlar arası hizmetleri sağlar. Services for UNIX dosya paylaşımı, uzaktan erişim ve yönetim, parola eşitleme, ortak dizin yönetimi, yardımcı programlar ortak bir dizi ve bir kabuk sağlar.  
  
 [Windows Services for UNIX](http://www.microsoft.com/downloads/details.aspx?FamilyID=896c9688-601b-44f1-81a4-02878ff11778&displaylang=en)  
  
### <a name="interopsystemscom"></a>InteropSystems.com  
 [http://www.interopsystems.com/](http://www.interopsystems.com/)  
  
 Taşıma UNIX'ten Win32 Destekli yazılım sağlayan bir şirket için site bir üçüncü taraf.  
  
### <a name="c-boost-web-site"></a>C++ Destek Web sitesi  
 [http://boost.sourceforge.NET/Regression-Logs/](http://boost.sourceforge.net/regression-logs/)  
  
 [http://boost.sourceforge.NET/boost-build2/](http://boost.sourceforge.net/boost-build2/)  
  
## <a name="porting-unix-applications-directly-to-win32"></a>UNIX uygulamalarını doğrudan Win32 bağlantı noktası oluşturma  
 Başka bir seçenek, UNIX uygulamalarını doğrudan Win32'ye taşıma. ANSI C/C++ kitaplıkları ve ticari C derleyicisi kitaplıkları kullanarak, birçok UNIX uygulamalarla üzerinde çağrıları iletilen geleneksel sistem Win32 uygulamalarda kullanılabilir.  
  
 Çıktı modelinin **stdio**-tabanlı uygulamaların API'leri taklit Win32 konsol beri değiştirilen gerekmez **stdio** modeli ve sürümleri *curses* kullanan mevcut Win32 konsol API'lerini. Daha fazla bilgi için bkz: [SetConsoleCursorPosition](http://msdn.microsoft.com/library/windows/desktop/ms686025).  
  
 Win32 uygulamaları olarak çalışmak için çok az değişiklik Berkeley yuva tabanlı uygulamalar gerekir. Windows Yuvaları arabirimi WinSock belirtimi giriş bölümlerde belirtilmiştir minimum değişiklikle BSD yuva ile taşınabilirlik için tasarlanmıştır.  
  
 RPC tabanlı uygulamaları kolayca kullanılabilir; bu nedenle Windows DCE uyumlu RPC'yi destekler. Bkz: [RPC işlevleri](http://msdn.microsoft.com/library/windows/desktop/aa378623).  
  
 En büyük fark alanlarından biri işlem modelinde biridir. UNIX **çatalı**; Win32 değildir. Kullanımına bağlı olarak **çatalı** ve kod temeli Win32 kullanılabilecek iki API vardır: **CreateProcess** ve `CreateThread`. Birden çok kopyalarını bölen UNIX uygulama içinde birden çok iş parçacığı ile tek bir işlem veya birden çok işlemler için Win32 yeniden. Birden çok işlem kullandıysanız, işlemler arasında iletişim kurmak için kullanılan IPC birden çok yöntemleri vardır (ve belki de kodu ve üst gibi olacak yeni işlem verilerini güncelleştirmek için işlevselliği, **çatalı** sağlar gereklidir). IPC hakkında daha fazla bilgi için bkz: [Ara işlem iletişimleri](http://msdn.microsoft.com/library/windows/desktop/aa365574).  
  
 Windows ve UNIX grafik modelleri çok farklıdır. Windows GDI kullanırken UNIX X Window System GUI kullanır. Kavramsal benzer olmalarına rağmen X API GDI API'ye basit eşlemesi yok. Bununla birlikte, OpenGL desteği geçirme UNIX OpenGL tabanlı uygulamalar için kullanılabilir. Ve X istemcileri ve sunucuları Windows için X. Bkz: [cihaz bağlamları](http://msdn.microsoft.com/library/windows/desktop/dd183553) GDI hakkında bilgi için.  
  
 Birçok CGI uygulaması gibi temel UNIX uygulamaları kolayca Windows üzerinde çalışan Visual C++ için bağlantı noktası. Gibi işlev **açmak**, `fopen`, **okuma**, **yazma** ve diğerleri Visual C++ Çalışma Zamanı Kitaplığı'nda kullanılabilir. Ayrıca, C UNIX API'ları ve Win32 API'ları arasında bire bir eşleme yoktur: **açmak** için **CreateFile**, **okuma** için **ReadFile**, **yazma** için **WriteFile**, `ioctl` için **DeviceIoControl**, **kapatmak** için **CloseFile**ve benzeri.  
  
## <a name="windows-posix-subsystem"></a>Windows POSIX alt sistemini  
 Başka bir seçenek UNIX programcıları bakma Windows POSIX alt sistemidir. Ancak, yalnızca Windows NT oluşturulduğunda standartlaştırılmış tek POSIX sürümü olan POSIX 1003.1 destekler. O zamandan bu yana olmamıştı bu alt sistemi genişletmek için çok az talep uygulamaların çoğu Win32'ye dönüştürüldüğünden olduğundan. Çok sayıda özellik içermediğinden 1003.1 tam özellikli uygulamalar için sınırlı ilgi sistemidir (olanlar 1003.2 içinde gibi ağ desteği vb.). Windows POSIX alt sistemini altında çalışan tam özellikli uygulamaların Windows özellikleri bellek eşlemeli dosyalar, ağ ve grafikler gibi Win32 uygulamalarına erişimi. Windows POSIX alt sistemini ana hedefleri uygulamalardır VI, LS ve GREP gibi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++ taşıma ve yükseltme Kılavuzu](visual-cpp-change-history-2003-2015.md)   
 [UNIX](../c-runtime-library/unix.md)   
 [Çıkarım Kuralları](../build/inference-rules.md)