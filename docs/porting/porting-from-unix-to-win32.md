---
title: UNIX'ten Win32'ye taşıma | Microsoft Docs
ms.custom: ''
ms.date: 08/02/2018
ms.technology:
- cpp-language
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ebfad8a86a1e26ecf4c78307bada673d81e46d9a
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50065440"
---
# <a name="porting-from-unix-to-win32"></a>UNIX'ten Win32'ye Bağlantı Noktası Oluşturma

Uygulamalar için Windows UNIX içinden geçiş için birkaç seçeneğiniz vardır:

- UNIX'ten Win32 uygulamalarına bağlantı noktası UNIX kitaplıklarını kullanma

- UNIX'ten Win32 uygulamaları yerel olarak taşıma

- POSIX alt sistemini kullanarak Windows üzerinde çalışan UNIX uygulamalar

## <a name="unix-libraries"></a>UNIX kitaplıkları

Bir seçenek UNIX programcılar normalde düşünün, UNIX kodu derleme bir Win32 çalıştırılabilir dosyası olarak izin vermek için üçüncü taraf UNIX benzeri kitaplıkları kullanıyor. Birçok ticari (ve en az bir ortak etki alanı) kitaplıkları bunu. Bazı uygulamalar için bir seçenek budur. Bu kitaplıkları taşıma avantajı, bunlar ilk taşıma çabasını en aza olmasıdır. Bir rekabet yazılım ürünü için ana olumsuz bir uygulamanın yerel bir Win32 bağlantı noktası genellikle daha hızlı olacak ve daha fazla işlevsellik kaçınılmaz olarak gerekir ' dir. Daha fazla güç Windows almak için Win32 çağrıları yapması gerektiğinde, UNIX kabuğunun dışında adım uygulamanın garip olabilir.

Aşağıdaki listede, Microsoft ve üçüncü taraf kaynakları taşıma ve UNIX geçiş Visual c++ destek sağlar:

### <a name="unix-migration-guides"></a>UNIX geçiş kılavuzları

[UNIX özel uygulama Geçiş Kılavuzu](https://technet.microsoft.com/library/bb656290.aspx) Teknik Yardım kod geçiş UNIX'ten Win32 ortamı sağlar.

[UNIX geçiş Proje Kılavuzu](https://technet.microsoft.com/library/bb656287.aspx) üst düzey Yardım geçirme önemli projeleri UNIX'ten Win32'ye sağlayarak UNIX özel uygulama geçiş kılavuzunu tamamlar. Kılavuz, her proje geçişi aşamasında göz önüne almanız gereken sorunlar hakkında öneriler sağlar.

### <a name="microsoft-windows-services-for-unix-sfu"></a>Microsoft Windows Services for UNIX (SFU)

Microsoft Windows Services for UNIX (SFU), çeşitli Windows, UNIX tabanlı mevcut ortamlardan tümleştirmeye yönelik platformlar arası hizmetleri sağlar. UNIX için Hizmetleri, dosya paylaşımı, uzaktan erişim ve yönetim, parola eşitleme, ortak dizin yönetimi, ortak bir araçlar kümesi ve bir kabuk sağlar.

[UNIX için Windows Hizmetleri](http://www.microsoft.com/downloads/details.aspx?FamilyID=896c9688-601b-44f1-81a4-02878ff11778&displaylang=en)

### <a name="interopsystemscom"></a>InteropSystems.com

[http://www.interopsystems.com/](http://www.interopsystems.com/)

Yazılım taşıma UNIX'ten Win32'destek sağlayan bir şirket için site bir üçüncü taraf.

### <a name="c-boost-web-site"></a>C++ Destek Web sitesi

[http://boost.sourceforge.net/regression-logs/](http://boost.sourceforge.net/regression-logs/)

[http://boost.sourceforge.net/boost-build2/](http://boost.sourceforge.net/boost-build2/)

## <a name="porting-unix-applications-directly-to-win32"></a>UNIX uygulamalarını doğrudan Win32 taşıma

Başka bir seçenek, UNIX uygulamalarını doğrudan Win32 taşımaktır. ANSI C/C++ kitaplıkları ve ticari C Derleyici kitaplıklarını kullanarak, birçok geleneksel sistem çağrıları UNIX uygulamalar tarafından yararlandı Win32 uygulamalarında kullanılabilir.

Çıktı modelinin **stdio**-tabanlı uygulamaları API'leri taklit Win32 konsol beri değiştirilmiş gerekmez **stdio** modeli ve sürümleri *curses* kullanan mevcut Win32 konsol API'leri. Daha fazla bilgi için [SetConsoleCursorPosition](https://msdn.microsoft.com/library/windows/desktop/ms686025).

Win32 uygulamaları olarak çalışmak için çok az değişiklik Berkeley yuva tabanlı uygulamaları gerekir. Windows Sockets arabirimini taşınabilirlik sayesinde WinSock belirtiminin giriş olarak bölümlerde belirtilmiştir minimum değişiklikle BSD yuva için tasarlanmıştır.

Windows uyumlu DCE RPC desteklediğinden, RPC-tabanlı uygulamaları kolayca kullanılabilir. Bkz: [RPC işlevleri](/windows/desktop/Rpc/rpc-functions).

En büyük alanlarından farkı, işlem modelinde yer alır. UNIX `fork`; Win32 değildir. Kullanımına bağlı olarak `fork` ve kod tabanının Win32 kullanılabilecek iki API vardır: `CreateProcess` ve `CreateThread`. Birden çok kopyalarını çatallar bir UNIX uygulama birden çok işlem ya da birden çok iş parçacığı ile tek bir işlem için Win32'de yeniden. Birden çok işlem kullandıysanız, işlemler arasında iletişim kurmak için kullanılan IPC, birden fazla yöntem vardır (ve belki de kod ve üst öğe gibi olması için yeni bir işlem verileri güncelleştirmek için İşlevler, `fork` sağlar gereklidir). IPC hakkında daha fazla bilgi için bkz. [Ara işlem iletişimleri](/windows/desktop/ipc/interprocess-communications).

Windows ve UNIX grafik modelleri çok farklıdır. GDI Windows kullanan UNIX X penceresi sistem GUI kullanır. Benzer kavramsal rağmen GDI API'sine X API'sinin basit eşlemesi yok. Ancak, OpenGL desteği geçirme UNIX OpenGL tabanlı uygulamalar için kullanılabilir. Ve X istemcileri ve sunucuları için Windows X. Bkz: [cihaz bağlamları](https://msdn.microsoft.com/library/windows/desktop/dd183553) GDI hakkında bilgi için.

Visual c++ Windows üzerinde çalışan çok CGI uygulaması gibi temel UNIX uygulamaları kolayca aktarılabilir. Gibi işlev `open`, `fopen`, `read`, `write` ve diğer Visual C++ Çalışma Zamanı Kitaplığı'nda kullanılabilir. Ayrıca, UNIX API'leri C ve Win32 API'ları arasında bire bir eşleme yoktur: `open` için `CreateFile`, `read` için `ReadFile`, `write` için `WriteFile`, `ioctl` için `DeviceIOControl`, `close` için`CloseFile`ve benzeri.

## <a name="windows-posix-subsystem"></a>Windows POSIX alt sistemi

Başka bir seçenek UNIX programcılar göz Windows POSIX alt sistemi ' dir. Ancak, yalnızca Windows NT oluşturulduğunda standartlaştırılmış yalnızca POSIX sürümün POSIX 1003.1 destekler. O zamandan bu yana var. Bu alt genişletmek için çok az talep nedeniyle çoğu uygulama için Win32 dönüştürüldü Çok sayıda özellik içermediğinden 1003.1 tam özellikli uygulamalar için sınırlı ilgi sistemidir (1003.2 penceresindekilerle gibi ağ desteği vb.). Windows POSIX altında çalışan tam özellikli uygulamaların Windows özelliklerine bellek eşlemeli dosyalar, ağ ve grafikler gibi Win32 uygulamalarına erişiminiz yok. VI ve LS GREP gibi Windows POSIX alt ana hedeflerini gösterilebilir.

## <a name="see-also"></a>Ayrıca Bkz.

[Visual C++ Taşıma ve Yükseltme Kılavuzu](visual-cpp-change-history-2003-2015.md)<br/>
[UNIX](../c-runtime-library/unix.md)<br/>
[Çıkarım Kuralları](../build/inference-rules.md)