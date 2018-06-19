---
title: UNIX kullanıcıları için Visual C++'a giriş | Microsoft Docs
ms.custom: ''
ms.date: 09/01/2017
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- UNIX [C++]
ms.assetid: 36108b31-e7fa-49a8-a1f7-7077fcbec873
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f05d7d3d3d3fd6b40a5477b7765b89409747d3ce
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33845872"
---
# <a name="introduction-to-visual-c-for-unix-users"></a>UNIX Kullanıcıları için Visual C++'a Giriş

Bu konu, Visual Studio için yenidir ve C++ ve Visual Studio tümleşik geliştirme ortamı (IDE) ile üretken isteyen UNIX kullanıcıları için bilgi sağlar.
  
## <a name="getting-started-on-the-command-line"></a>Komut satırında Başlarken  

C++ derleyicisi komut satırından UNIX komut satırı ortamı kullanacağınız benzer şekilde kullanabilirsiniz. Komut satırı C ve C++ derleyicisi (CL. kullanarak komut satırından derleme EXE), bağlayıcı (bağlantı. EXE) ve diğer NMAKE,. EXE, UNIX Microsoft sürümü yardımcı olun.  
  
UNIX komutları/usr/bin gibi bir ortak klasöre yüklenir. Visual Studio'da komut satırı araçları, Visual Studio yükleme dizininde VC\bin alt ve alt dizinlerinde yüklenir. UNIX farklı olarak bu araçlar düz bir komut istemi penceresinde kullanılabilir değil. Komut satırı araçları, bir geliştirici komut istemi kısayol kullanma veya Çalıştır kullanmak için geliştirici komut dosyası vcvarsall.bat gibi. Bu yolu ve C++ programları komut satırından derlemek için gerekli olan diğer ortam değişkenlerini ayarlar. Daha fazla bilgi için bkz: [komut satırında C/C++ derleme kodu](../build/building-on-the-command-line.md) ve [izlenecek yol: komut satırında yerel C++ programı derleme](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md).  
  
Bir geliştirici komut istemi kısayoluna açmak için girin *Geliştirici komut istemi* masaüstünde denetimi arayın ve seçin **Geliştirici komut istemi** Visual Studio sürümünüze sonucu. Belirli bir konağa ve hedef mimari için önceden yapılandırılmış bir geliştirici komut istemi seçmek için açık **Başlat** menüsü (Windows simgesi Masaüstü köşesinde) ve Visual Studio sürümünüze klasöre kaydırma yapın , aşağıdaki gibi **Visual Studio 2017**. Klasörü açın ve tercih edilen konak ve hedef Mimarinizi komut istemi kısayoluna seçin.
  
Daha güçlü avantajlarından yararlanmak için Visual Studio hata ayıklayıcısı, IntelliSense kod arama ve deyim tamamlama, görsel tasarımcılar gibi özellikleri proje yönetimine ve vb., Visual Studio IDE kullanmanız gerekir.  
  
## <a name="debugging-your-code"></a>Kodunuzun hatalarını ayıklama  

Komut satırını kullanın ve uygulamalarınızı geliştirme iş istasyonunuza çalıştırmak, göreceksiniz çalıştırmak için bir iletişim kutusu [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] hata ayıklayıcı kodunuzu bellek erişim ihlali, işlenmeyen bir özel durum veya diğer kurtarılamaz karşılaştığında görüntülenir hatalar. Tıklatırsanız **Tamam**, Visual Studio geliştirme ortamında başlatılır ve hata ayıklayıcısı hata noktasına açılacaktır. Bu şekilde uygulamalarınızda hata ayıklamak mümkündür ve bu durumda, kaynak kodunuz yalnızca ile derlenmiş ise kullanılabilir olur [/Z7, / zi, /zı (hata ayıklama bilgileri biçimi)](../build/reference/z7-zi-zi-debug-information-format.md) geçin. Daha fazla bilgi için bkz: [yerel kod hata ayıklama](/visualstudio/debugger/debugging-native-code) ve [C++ Masaüstü geliştirmesi için Visual Studio IDE kullanarak](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  
  
## <a name="using-the-development-environment"></a>Geliştirme ortamını kullanma  

Geliştirme ortamı düzenleyin ve kaynak kodunuzu yapı içinde kullanmak daha kolay bir *proje*. Proje, kaynak ve bir kitaplık veya yürütülebilir dosya gibi tek bir birime derlenmiş ilişkili dosyaları koleksiyonudur. Bir proje nasıl oluşturulacak dosyalardır hakkında bilgiler de içerir. Projeler hakkında bilgi uzantısı .prj bir proje dosyasında depolanır.  
  
Birden çok kitaplıkları ve yürütülebilir dosyaları, her olası derleyici seçenekleri ya da farklı bir dilde farklı bir kümesiyle yerleşik oluşan bir uygulama, tek bir parçası olan birden çok proje depolanır *çözüm*. Birden çok proje gruplamak için bir kapsayıcı için bir Özet bir çözümdür. Çözümleri hakkında bilgi .sln uzantılı bir çözüm dosyasında depolanır. Daha fazla bilgi için bkz: [çözümler ve projeler Visual Studio'da](/visualstudio/ide/solutions-and-projects-in-visual-studio) ve [C++ Masaüstü geliştirmesi için Visual Studio IDE kullanarak](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  
  
## <a name="importing-your-existing-code"></a>Varolan kod içeri aktarma 
 
C++ derleyicisi ile veya bir derleme görevleri dosyası olmadan derlemek ve içine yerleştirmek için ayarlanmış var olan kodu oluşturmak için kullanabileceğiniz bir [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] projesi. Daha fazla bilgi için bkz: [nasıl yapılır: Varolan koddan C++ projesi oluşturma](../ide/how-to-create-a-cpp-project-from-existing-code.md).  
  
## <a name="creating-a-new-project"></a>Yeni proje oluşturma  

Geliştirme ortamında yeni projeler oluşturabilir. Visual Studio çeşitli ortak görevler için standart kod sağlayan çok sayıda şablonları sağlar. Uygulama sihirbazları çeşitli uygulama türleri için kod anahatlarıyla projeler oluşturmak için kullanabilirsiniz.  
  
Boş bir proje ile kullanarak başlatabilirsiniz **konsol uygulaması (Win32) Sihirbazı**. Seçin **boş proje** onay kutusu. Daha sonra yeni ve mevcut dosyaları projeye sonra ekleyebilirsiniz.  
  
Bir proje oluşturduğunuzda, projeyi adlandırmanız gerekir. Varsayılan olarak, dinamik bağlantı kitaplığı (DLL) adını proje adı eşittir veya projeden olan yürütülebilir. Daha fazla bilgi için bkz: [oluşturma çözümler ve projeler](/visualstudio/ide/creating-solutions-and-projects).  
  
## <a name="microsoft-specific-modifiers"></a>Microsoft'a Özgü Değiştiriciler  

Microsoft Visual C++ Derleyici programlama Windows işletim sistemlerinde desteklemek için programlama dili standart C++ için birkaç uzantıları uygular. Bu uzantılar çağırma kurallarına işlev depolama sınıfı öznitelikler belirtmek için kullanılır ve tabanlı adresleme, diğerlerinin yanında. Tüm desteklenen C++ uzantılarının tam listesi için bkz: [Microsoft'a özgü değiştiriciler](../cpp/microsoft-specific-modifiers.md).  
  
Kullanarak tüm Microsoft özgü uzantılar c++ devre dışı bırakabilirsiniz **/Za** derleyici seçeneği. Birden çok platformu üzerinde çalıştırmak için kod yazmak istiyorsanız bu seçeneği önerilir. Daha fazla bilgi için **/Za** derleyici seçeneği bkz [/Za, /Ze (dil uzantılarını devre dışı bırak)](../build/reference/za-ze-disable-language-extensions.md). C++ Derleyici uyumluluğu hakkında daha fazla bilgi için bkz: [Visual C++ dili uygunluk](../visual-cpp-language-conformance.md) ve [standart dışı davranış](../cpp/nonstandard-behavior.md).  
  
## <a name="precompiled-headers"></a>Önceden derlenmiş üst bilgileri  

Microsoft C ve C++ Derleyicileri satır içi kod dahil olmak üzere tüm C veya C++ kodu önceden derlemek için seçenekler sağlar. Bu performans özelliğini kullanarak, kod kararlı gövdesi, kod derlenmiş durumu bir dosyada saklayabilir ve, sonraki derlemeler sırasında önceden derlenmiş kod halen geliştirilme aşamasındadır kodu ile birleştirin. Sonraki her derleme daha hızlı çünkü tutarlı kodun derlenmesi gerekmez.  
  
Varsayılan olarak, tüm önceden derlenmiş kod dosyalarında belirtilir **stdafx.h** ve **stdafx.cpp**. **Yeni proje** Sihirbazı otomatik olarak oluşturacak bu dosyaları sizin için kaldırmadıysanız **önceden derlenmiş üstbilgi** seçeneği. Önceden derlenmiş üst bilgileri hakkında daha fazla bilgi için bkz: [önceden derlenmiş üst bilgi dosyaları oluşturma](../build/reference/creating-precompiled-header-files.md).  
  
## <a name="related-sections"></a>İlgili Bölümler  

Daha fazla bilgi için bkz: [UNIX'ten Win32'ye taşıma](../porting/porting-from-unix-to-win32.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[C/C++ Programları Oluşturma](../build/building-c-cpp-programs.md)