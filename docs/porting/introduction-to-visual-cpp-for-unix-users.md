---
title: UNIX Kullanıcıları için Visual C++'a Giriş
ms.date: 09/01/2017
helpviewer_keywords:
- UNIX [C++]
ms.assetid: 36108b31-e7fa-49a8-a1f7-7077fcbec873
ms.openlocfilehash: 7f73e51e02eafe46c279a8f828803912d8cd190a
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/20/2019
ms.locfileid: "69631690"
---
# <a name="introduction-to-visual-c-for-unix-users"></a>UNIX Kullanıcıları için Visual C++'a Giriş

Bu konu, Visual Studio 'ya yeni eklenen ve Visual Studio tümleşik geliştirme ortamı (IDE) ile C++ üretken olmak isteyen UNIX kullanıcıları için bilgi sağlamaktadır.

## <a name="getting-started-on-the-command-line"></a>Komut satırına Başlarken

Derleyiciyi, C++ komut satırından UNIX komut satırı ortamı kullanacak şekilde kullanabilirsiniz. Komut isteminden, komut satırı C ve C++ derleyicisini kullanarak derleyebilirsiniz (CL. EXE), bağlayıcı (LINK. EXE) ve NMAKE dahil diğer araçları. EXE, UNIX Make 'in Microsoft sürümü yardımcı programıdır.

UNIX 'te komutlar,/usr/bingibi ortak bir klasöre yüklenir. Visual Studio 'da, komut satırı araçları VC\bin alt dizinindeki ve alt dizinlerinde Visual Studio yükleme dizinine yüklenir. UNIX 'ten farklı olarak, bu araçlar düz bir komut istemi penceresinde kullanılamaz. Komut satırı araçlarını kullanmak için, bir geliştirici komut istemi kısayolunu kullanın veya vcvarsall. bat gibi bir geliştirici komut dosyası çalıştırın. Bu, komut satırından programları derlemek C++ için gereken yolu ve diğer ortam değişkenlerini ayarlar. Daha fazla bilgi için bkz. [komut satırındaC++ C/kod oluşturma](../build/building-on-the-command-line.md) ve [izlenecek yol: Komut satırında](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)yerel C++ bir program derleniyor.

Geliştirici komut istemi kısayolunu açmak için, masaüstü arama denetimine *Geliştirici komut istemi* girin ve Visual Studio sürümünüz için **Geliştirici komut istemi** sonucunu seçin. Belirli bir konak ve hedef mimari için önceden yapılandırılmış bir geliştirici komut istemi seçmek için **Başlat** menüsünü açın (masaüstünün köşesindeki Windows simgesi) ve Visual Studio sürümünüz için görsel gibi klasöre kaydırın.  **Studio 2017**. Klasörü açın ve tercih ettiğiniz konak ve hedef mimariniz için komut istemi kısayolunu seçin.

Visual Studio hata ayıklayıcısı, IntelliSense kod arama ve ekstre tamamlama, görsel tasarımcılar, proje yönetimi vb. gibi daha güçlü özelliklerden yararlanmak için Visual Studio IDE 'yi kullanmanız gerekir.

## <a name="debugging-your-code"></a>Kodunuzda hata ayıklama

Komut satırını kullanır ve uygulamalarınızı geliştirme iş istasyonunuzda çalıştırırsanız, kodunuz bir bellek erişim ihlali, işlenmeyen özel durum veya kurtarılamaz diğer bir hatayla karşılaştığında Visual Studio hata ayıklayıcısı 'nı çalıştırmak için bir iletişim kutusunun görüntülendiğini görürsünüz. hatası. **Tamam**' a tıkladığınızda, Visual Studio geliştirme ortamı başlatılır ve hata ayıklayıcı hata noktasına açılır. Uygulamalarınızın bu şekilde hata ayıklaması yapılabilir ve bu durumda kaynak kodunuz yalnızca [/Z7,/Zi,/ZI (hata ayıklama bilgileri biçimi)](../build/reference/z7-zi-zi-debug-information-format.md) anahtarıyla derlenmişse kullanılabilir. Daha fazla bilgi için bkz. [yerel kodda hata ayıklama](/visualstudio/debugger/debugging-native-code) ve [masaüstü geliştirme IÇIN C++ Visual Studio IDE 'yi kullanma](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).

## <a name="using-the-development-environment"></a>Geliştirme ortamını kullanma

Bir *projede*kaynak kodunuzu düzenlemek ve derlemek için geliştirme ortamının kullanılması daha kolaydır. Proje, bir kitaplık veya yürütülebilir dosya gibi tek bir birimde derlenecek kaynak ve ilgili dosyalar koleksiyonudur. Proje ayrıca dosyaların nasıl derlenildiği hakkında bilgiler içerir. Projeler hakkındaki bilgiler,. PRJ uzantısına sahip bir proje dosyasında depolanır.

Birden çok kitaplık ve yürütülebilirden oluşan, her biri farklı bir derleyici seçenekleri kümesiyle veya farklı bir dilde oluşturulmuş olan bir uygulama, tek bir *çözümün*parçası olan birden çok projede depolanır. Çözüm, bir kapsayıcının birden çok projeyi birlikte gruplamak için soyutlamadır. Çözümler hakkında bilgi. sln uzantılı bir çözüm dosyasında depolanır. Daha fazla bilgi için bkz. [Visual Studio 'Da çözümler ve projeler](/visualstudio/ide/solutions-and-projects-in-visual-studio) ve [masaüstü geliştirme IÇIN C++ Visual Studio IDE 'yi kullanma](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).

## <a name="importing-your-existing-code"></a>Mevcut kodunuzu içeri aktarma

Derleyicisini, C++ derleme görevleri dosyası olmadan veya bir Visual Studio projesine koyabilmek üzere ayarlanmış mevcut kodu oluşturmak için kullanabilirsiniz. Daha fazla bilgi için [nasıl yapılır: Varolan koddan C++ ](../build/how-to-create-a-cpp-project-from-existing-code.md)bir proje oluşturun.

## <a name="creating-a-new-project"></a>Yeni proje oluşturma

Geliştirme ortamında yeni projeler oluşturabilirsiniz. Visual Studio çeşitli ortak projeler için standart kod sağlayan çok sayıda şablon sağlar. Çeşitli uygulama türleri için kod anahatlarıyla projeler oluşturmak üzere uygulama sihirbazları kullanabilirsiniz.

**Konsol uygulaması (Win32) sihirbazını**kullanarak boş bir proje ile başlayabilirsiniz. **Boş proje** onay kutusunu seçin. Daha sonra projeye yeni ve var olan dosyaları daha sonra ekleyebilirsiniz.

Bir proje oluşturduğunuzda, projeyi adı vermelisiniz. Varsayılan olarak, proje adı dinamik bağlantı kitaplığının (DLL) ya da projeden yapı olan yürütülebilir dosyanın adına eşit olur. Daha fazla bilgi için bkz. [çözüm ve proje oluşturma](/visualstudio/ide/creating-solutions-and-projects).

## <a name="microsoft-specific-modifiers"></a>Microsoft'a Özgü Değiştiriciler

Microsoft C++ derleyicisi, Windows işletim sistemlerine yönelik programlamayı desteklemek C++ için standart programlama diline birkaç uzantı uygular. Bu uzantılar depolama sınıfı özniteliklerini, işlev çağırma kurallarını ve temel adresleme 'yi diğer şeyler arasında belirtmek için kullanılır. Desteklenen C++ tüm uzantıların tam listesi için bkz. [Microsoft 'a özgü değiştiriciler](../cpp/microsoft-specific-modifiers.md).

`/Za` Derleyici seçeneğini kullanarak, için Microsoft 'a C++ özgü tüm uzantıları devre dışı bırakabilirsiniz. Birden çok platformda çalıştırmak üzere kod yazmak istiyorsanız bu seçenek önerilir. `/Za` Derleyici seçeneği hakkında daha fazla bilgi için bkz. [/za,/Ze (dil uzantılarını devre dışı bırak)](../build/reference/za-ze-disable-language-extensions.md). Derleyici uyumluluğu hakkında C++ daha fazla bilgi için bkz [. C++ görsel dil uyumluluğu](../overview/visual-cpp-language-conformance.md) ve [Standart olmayan davranış](../cpp/nonstandard-behavior.md).

## <a name="precompiled-headers"></a>Önceden derlenmiş üstbilgiler

Microsoft C ve C++ derleyicileri, satır içi kod dahil olmak üzere herhangi C++ bir C veya kodu önceden derlemek için seçenekler sağlar. Bu performans özelliğini kullanarak kodun kararlı bir gövdesini derleyebilir, kodun derlenmiş durumunu bir dosyada saklayabilir ve sonraki derlemeler sırasında, önceden derlenmiş kodu, hala geliştirme aşamasında olan kodla birleştirebilirsiniz. Kararlı kodun yeniden derlenmesi gerekmediğinden, sonraki her derleme daha hızlıdır.

Varsayılan olarak, tüm önceden derlenmiş kod, *pch. h* ve *pch. cpp* dosyalarında belirtilmiştir (Visual Studio 2017 ve önceki sürümlerde stdadfx *. h* ve *stdadfx. cpp* ). **Yeni proje** Sihirbazı, **ön derlenmiş üstbilgi** seçeneğinin işaretini kaldırmadığınız takdirde sizin için otomatik olarak bu dosyaları oluşturur. Önceden derlenmiş üstbilgiler hakkında daha fazla bilgi için bkz. [önceden derlenmiş üst bilgi dosyaları oluşturma](../build/creating-precompiled-header-files.md).

## <a name="related-sections"></a>İlgili Bölümler

Daha fazla bilgi için bkz. [UNIX 'Ten Win32 'e taşıma](../porting/porting-from-unix-to-win32.md).

## <a name="see-also"></a>Ayrıca bkz.

[Projeler ve derleme sistemleri](../build/projects-and-build-systems-cpp.md)
