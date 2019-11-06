---
title: UNIX kullanıcıları için C++ Microsoft 'a giriş
ms.date: 10/23/2019
helpviewer_keywords:
- UNIX [C++]
ms.assetid: 36108b31-e7fa-49a8-a1f7-7077fcbec873
ms.openlocfilehash: 791c513553acbd300204746ae1e1dddf7a3ae5c4
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626995"
---
# <a name="introduction-to-microsoft-c-for-unix-users"></a>UNIX kullanıcıları için C++ Microsoft 'a giriş

Bu konu, Visual Studio 'ya yeni eklenen UNIX 'in tüm özellikleri hakkında bilgi sağlar ve komut satırından veya Visual Studio 'Yu kullanarak üretken C++ olmak ister. Windows 'a hedeflemek için Visual Studio 'Yu Microsoft C++ derleyicisi ile birlikte kullanabilirsiniz. Visual Studio IDE 'yi, uzak Linux makineleri, MinGW-W64 ve Linux için Windows alt sistemi gibi UNIX ortamlarında GCC veya Clang ile de kullanabilirsiniz. Visual Studio C++ 'da kullanmak için iş yükü **ile C++ masaüstü geliştirme** 'nın yüklü olması gerekir. İş yükünü yüklemek veya isteğe bağlı bileşenleri eklemek veya kaldırmak için Visual Studio Yükleyicisi açın. Ayrıca, uzak bir Linux makinesini hedefliyorsanız, iş yüküyle **Linux geliştirmeyi C++**  de yükleyebilirsiniz. Android veya iOS geliştirmesi için iş yüküyle **mobil geliştirme C++**  ' yi yükler.

## <a name="getting-started-on-the-command-line"></a>Komut satırına Başlarken

Microsoft C++ derleyicisini, komut satırından UNIX komut satırı ortamı kullanacak şekilde kullanabileceğiniz şekilde kullanabilirsiniz. Komut isteminden, komut satırı C ve C++ derleyicisini kullanarak derleyebilirsiniz (CL. EXE), bağlayıcı (LINK. EXE) ve NMAKE dahil diğer araçları. EXE, UNIX Make 'in Microsoft sürümü yardımcı programıdır.

UNIX 'te komutlar,/usr/bingibi ortak bir klasöre yüklenir. Visual Studio 'da, komut satırı araçları VC\bin alt dizinindeki ve alt dizinlerinde Visual Studio yükleme dizinine yüklenir. UNIX 'ten farklı olarak, bu araçlar düz bir komut istemi penceresinde kullanılamaz. Komut satırı araçlarını kullanmak için, programları derlemek C++ için gereken yolu ve diğer ortam değişkenlerini ayarlayan özel bir geliştirici komut istemi kullanmanız gerekir. Daha fazla bilgi için bkz. komut [satırındaC++ C/Code oluşturma](../build/building-on-the-command-line.md) ve [Izlenecek yol: komut satırında yerel C++ bir program](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)derleme.

## <a name="debugging-your-code"></a>Kodunuzda hata ayıklama

Microsoft C++ projeleri Için Visual Studio hata ayıklayıcısını, komut SATıRıNDAN veya IDE içinden kullanabilirsiniz. Kaynaklardaki adımlamayı etkinleştirmek için [/Z7,/Zi,/ZI (hata ayıklama bilgileri biçimi)](../build/reference/z7-zi-zi-debug-information-format.md) anahtarıyla derleyin. Daha fazla bilgi için bkz. [yerel kodda hata ayıklama](/visualstudio/debugger/debugging-native-code) ve [masaüstü geliştirme IÇIN C++ Visual Studio IDE 'yi kullanma](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).

GCC veya Clang ile derlenen programlar için, Visual Studio GDB 'yi, LLDB 'yi veya belirttiğiniz özel hata ayıklayıcıyı çağırır.

## <a name="visual-studio-project-system"></a>Visual Studio proje sistemi

Visual Studio proje sistemine MSBuild adı verilir. Proje dosyalarını XML biçiminde kullanır; C++ proje dosyaları. vcxproj uzantısına sahiptir. Birden çok kitaplık ve yürütülebilirden oluşan, her biri farklı bir derleyici seçenekleri kümesiyle veya farklı bir dilde oluşturulmuş olan bir uygulama, tek bir *çözümün*parçası olan birden çok projede depolanır. Çözüm, bir kapsayıcının birden çok projeyi birlikte gruplamak için soyutlamadır. Çözümler hakkında bilgi. sln uzantılı bir çözüm dosyasında depolanır. Daha fazla bilgi için bkz. [Visual Studio 'Da çözümler ve projeler](/visualstudio/ide/solutions-and-projects-in-visual-studio) ve [masaüstü geliştirme IÇIN C++ Visual Studio IDE 'yi kullanma](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md). Kullanılabilir Visual Studio proje şablonlarını görmek için ana menüden **dosya** > **Yeni** > **projesi** öğesini seçin.

Visual Studio 2017 ' den başlayarak, CMake projelerine yönelik destek eklendi ve Microsoft C++ derleyicisini herhangi bir rastgele derleme sistemiyle veya bir kaynak dosya ve proje dosyası olmayan bir klasörle kullanma seçenekleri eklenmiştir. Daha fazla bilgi için bkz. Visual Studio ['Da CMake projeleri](../build/cmake-projects-in-visual-studio.md) ve [Visual Studio 'Da klasör projelerini açma](../build/open-folder-projects-cpp.md).

## <a name="microsoft-specific-modifiers"></a>Microsoft'a özgü değiştiriciler

Microsoft C++ derleyicisi, Windows işletim sistemlerine yönelik programlamayı desteklemek C++ için standart programlama diline birkaç uzantı uygular. Bu uzantılar depolama sınıfı özniteliklerini, işlev çağırma kurallarını ve temel adresleme 'yi diğer şeyler arasında belirtmek için kullanılır. Desteklenen C++ tüm uzantıların tam listesi için bkz. [Microsoft 'a özgü değiştiriciler](../cpp/microsoft-specific-modifiers.md).

`/Za` derleyici seçeneğini kullanarak, Microsoft 'a C++ özgü tüm uzantıları devre dışı bırakabilirsiniz. Birden çok platformda çalıştırmak üzere kod yazmak istiyorsanız bu seçenek önerilir. `/Za` derleyici seçeneği hakkında daha fazla bilgi için bkz. [/za,/Ze (dil uzantılarını devre dışı bırak)](../build/reference/za-ze-disable-language-extensions.md). Derleyici uyumluluğu hakkında C++ daha fazla bilgi için bkz. [Microsoft C++ dil uygunluk tablosu](../overview/visual-cpp-language-conformance.md) ve [Standart olmayan davranış](../cpp/nonstandard-behavior.md).

## <a name="precompiled-headers"></a>Önceden derlenmiş üstbilgiler

Microsoft C ve C++ derleyicileri, satır içi kod dahil olmak üzere herhangi C++ bir C veya kodu önceden derlemek için seçenekler sağlar. Bu performans özelliğini kullanarak kodun kararlı bir gövdesini derleyebilir, kodun derlenmiş durumunu bir dosyada saklayabilir ve sonraki derlemeler sırasında, önceden derlenmiş kodu, hala geliştirme aşamasında olan kodla birleştirebilirsiniz. Kararlı kodun yeniden derlenmesi gerekmediğinden, sonraki her derleme daha hızlıdır.

Varsayılan olarak, tüm önceden derlenmiş kod, *pch. h* ve *pch. cpp* dosyalarında belirtilmiştir (Visual Studio 2017 ve önceki sürümlerde*stdadfx. h* ve *stdadfx. cpp* ). Önceden derlenmiş üstbilgiler hakkında daha fazla bilgi için bkz. [önceden derlenmiş üst bilgi dosyaları oluşturma](../build/creating-precompiled-header-files.md).

## <a name="related-sections"></a>İlgili bölümler

Daha fazla bilgi için bkz. [Windows 'Da Linux programlarını çalıştırma](../porting/porting-from-unix-to-win32.md).

## <a name="see-also"></a>Ayrıca bkz.

[Projeler ve derleme sistemleri](../build/projects-and-build-systems-cpp.md)
