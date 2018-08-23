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
ms.openlocfilehash: d5789e353a6e15d4da3f5754d9d4d91821359d14
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42465458"
---
# <a name="introduction-to-visual-c-for-unix-users"></a>UNIX Kullanıcıları için Visual C++'a Giriş

Bu konuda, C++ ve Visual Studio tümleşik geliştirme ortamı (IDE) ile üretken olmak ve Visual Studio'yu ilk kez UNIX kullanıcıları için bilgiler sağlar.
  
## <a name="getting-started-on-the-command-line"></a>Komut satırında kullanmaya başlama  

C++ derleyicisi komut satırından UNIX komut satırı ortamını kullanacağınız benzer şekilde kullanabilirsiniz. Komut satırı C ve C++ derleyicisi (CL. kullanarak komut satırından derleme EXE), bağlayıcı (bağlantı. EXE) ve diğer NMAKE,. EXE UNIX Microsoft sürümünü yardımcı olun.  
  
UNIX, komutları, / usr/bin gibi bir ortak klasöre yüklenir. Visual Studio komut satırı araçları, Visual Studio yükleme dizininde VC\bin alt ve alt dizinlerinde yüklenir. UNIX, bu araçlar düz bir komut istemi penceresinde kullanılamaz. Komut satırı araçları, bir geliştirici komut istemi kısayolunun kullanın veya çalışma kullanmak için bir geliştirici komut dosyası vcvarsall.bat gibi. Bu yolu ve C++ programları komut satırından derleme için gerekli olan diğer ortam değişkenlerini ayarlar. Daha fazla bilgi için [komut satırında C/C++ derleme kodu](../build/building-on-the-command-line.md) ve [izlenecek yol: komut satırında yerel C++ programı derleme](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md).  
  
Bir geliştirici komut istemi kısayolunun açmak için girin *Geliştirici komut istemi* Desktop denetimini arayın ve seçin **Geliştirici komut istemi** Visual Studio sürümünüz için sonuç. Belirli konak ve hedef mimari için önceden yapılandırılmış bir geliştirici Komut İstemi'ni seçmek için açık **Başlat** menü (Windows simge Masaüstü üst köşesinde) ve Visual Studio sürümünüz için klasörüne kaydırma yapın , aşağıdaki gibi **Visual Studio 2017**. Klasörü açmak ve tercih edilen konak ve hedef mimari için komut istemi kısayolunun seçin.
  
Daha güçlü yararlanmak için Visual Studio hata ayıklayıcısı, IntelliSense kod arama ve deyim tamamlama, görsel tasarımcılar gibi özellikleri proje yönetimi ve bu şekilde, Visual Studio IDE kullanmanız gerekir.  
  
## <a name="debugging-your-code"></a>Kodunuzun hatalarını ayıklama  

Komut satırını kullanın ve uygulamalarınızı geliştirme iş istasyonunuzda çalıştırmak, kodunuzu bir erişim ihlali, İşlenmeyen özel durum veya kurtarılamaz diğer karşılaştığında Visual Studio hata ayıklayıcıyı çalıştırmak için bir iletişim kutusu görüntülenir görürsünüz hataları. Tıklarsanız **Tamam**, Visual Studio geliştirme ortamını başlatılır ve hata ayıklayıcı hata noktasını için açılır. Bu şekilde uygulamalarınızda hata ayıklamak mümkündür ve bu durumda, kaynak kodunuzu yalnızca ile derlenmişse kullanılabilirdi [/z7, / zi, /zı (hata ayıklama bilgileri biçimi)](../build/reference/z7-zi-zi-debug-information-format.md) geçin. Daha fazla bilgi için [yerel kodda hata ayıklama](/visualstudio/debugger/debugging-native-code) ve [C++ Masaüstü geliştirmesi için Visual Studio IDE kullanarak](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  
  
## <a name="using-the-development-environment"></a>Geliştirme ortamını kullanma  

Geliştirme ortamı düzenleyin ve kaynak kodunuzu yapı içinde kullanımı daha kolay bir *proje*. Bir proje, kaynak ve bir kitaplık veya yürütülebilir dosya gibi tek bir birim içine derlenmiş ilişkili dosyaları koleksiyonudur. Bir proje, ayrıca dosyaların oluşturulacak şeklini hakkında bilgi içerir. Projeler hakkında bilgi uzantısı .prj ile bir proje dosyasında depolanır.  
  
Birden çok kitaplıkları ve her olabilecek birtakım farklı derleyici seçenekleri veya hatta farklı bir dil ile oluşturulmuş yürütülebilir dosyaları içeren bir uygulama, tek bir parçası olan birden çok proje depolanan *çözüm*. Bir çözüm, birden çok proje gruplamak bir kapsayıcı için bir soyutlamadır. Çözümleri hakkında bilgi, bir çözüm uzantısı .sln dosyasında depolanır. Daha fazla bilgi için [Visual Studio'da projeler ve çözümler](/visualstudio/ide/solutions-and-projects-in-visual-studio) ve [C++ Masaüstü geliştirmesi için Visual Studio IDE kullanarak](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  
  
## <a name="importing-your-existing-code"></a>Mevcut kod alma 
 
C++ derleyicisi ile veya bir derleme görevleri dosyası olmadan derleyin ve Visual Studio projesi yerleştirmek için ayarlanmış mevcut bir kod oluşturmak için kullanabilirsiniz. Daha fazla bilgi için [nasıl yapılır: Varolan koddan C++ projesi oluşturma](../ide/how-to-create-a-cpp-project-from-existing-code.md).  
  
## <a name="creating-a-new-project"></a>Yeni proje oluşturma  

Geliştirme ortamında yeni projeler oluşturabilirsiniz. Visual Studio standart kod sağlayan çeşitli ortak görevler için çeşitli şablonları sağlar. Uygulama sihirbazları, çeşitli uygulama türleri için kod anahatlarıyla projeler oluşturmak için kullanabilirsiniz.  
  
Boş bir proje ile kullanarak başlatabilirsiniz **konsol uygulaması (Win32) Sihirbazı**. Seçin **boş proje** onay kutusu. Ardından yeni ve mevcut dosyalar projeye daha sonra ekleyebilirsiniz.  
  
Bir proje oluşturduğunuzda, projeyi adlandırın gerekir. Varsayılan olarak dinamik bağlantı kitaplığı (DLL) adı proje adı'değerine eşit veya projeden olan yürütülebilir. Daha fazla bilgi için [projeler ve çözümler oluşturma](/visualstudio/ide/creating-solutions-and-projects).  
  
## <a name="microsoft-specific-modifiers"></a>Microsoft'a Özgü Değiştiriciler  

Microsoft Visual C++ derleyicisi, Windows işletim sistemleri için programlamayı desteklemek için programlama dili standart C++ birkaç uzantı uygular. Bu uzantılar, çağırma kuralları işlev depolama sınıfı öznitelikleri belirtmek için kullanılır ve tabanlı adresleme, diğerlerinin yanında. Desteklenen tüm C++ uzantıları tam bir listesi için bkz. [Microsoft'a özel değiştiriciler](../cpp/microsoft-specific-modifiers.md).  
  
Kullanarak tüm Microsoft özel C++ uzantılarını devre dışı bırakabilirsiniz `/Za` derleyici seçeneği. Birden çok platformda çalışacak kod yazmak istiyorsanız, bu seçenek önerilir. Daha fazla bilgi için `/Za` derleyici seçeneği bkz [/Za, /Ze (dil uzantılarını devre dışı bırak)](../build/reference/za-ze-disable-language-extensions.md). C++ Derleyici uyumluluğu hakkında daha fazla bilgi için bkz. [Visual C++ dil uyumluluğu](../visual-cpp-language-conformance.md) ve [standart dışı davranış](../cpp/nonstandard-behavior.md).  
  
## <a name="precompiled-headers"></a>Önceden derlenmiş üst bilgiler  

Microsoft C and C++ Derleyicileri, satır içi kod dahil olmak üzere tüm C veya C++ kodu önceden derlemek için seçenekler sağlar. Bu performans özelliği kullanarak, kod kararlı gövdesi, kodun derlenmiş hali bir dosyada depolar ve, sonraki derleme sırasında önceden derlenmiş kod hala geliştirilmekte olan kod ile birleştirin. Tutarlı kodun derlenmesi gerekmez çünkü her sonraki derleme daha hızlıdır.  
  
Varsayılan olarak, tüm önceden derlenmiş kod dosyaları stdafx.h ve stdafx.cpp belirtilir. **Yeni proje** Sihirbazı otomatik olarak oluşturur bu dosyaları sizin için kaldırmadıysanız **önceden derlenmiş üst bilgi** seçeneği. Önceden derlenmiş üst bilgiler hakkında daha fazla bilgi için bkz. [önceden derlenmiş üst bilgi dosyaları oluşturma](../build/reference/creating-precompiled-header-files.md).  
  
## <a name="related-sections"></a>İlgili Bölümler  

Daha fazla bilgi için [UNIX'ten Win32'ye taşıma](../porting/porting-from-unix-to-win32.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[C/C++ Programları Oluşturma](../build/building-c-cpp-programs.md)