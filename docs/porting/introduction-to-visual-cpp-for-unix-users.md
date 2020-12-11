---
description: "Daha fazla bilgi edinin: UNIX kullanıcıları için Microsoft C++ ' a giriş"
title: UNIX Kullanıcıları için Microsoft C++'a Giriş
ms.date: 10/23/2019
helpviewer_keywords:
- UNIX [C++]
ms.assetid: 36108b31-e7fa-49a8-a1f7-7077fcbec873
ms.openlocfilehash: 1047ba4e07803bfd6863a0b7da5d0e8473938586
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159836"
---
# <a name="introduction-to-microsoft-c-for-unix-users"></a>UNIX Kullanıcıları için Microsoft C++'a Giriş

Bu konu, Visual Studio 'ya yeni eklenen UNIX 'in tüm özellikleri hakkında bilgi sağlar ve C++ ile komut satırından ya da Visual Studio kullanarak üretken olmak ister. Windows hedeflemek için Visual Studio 'Yu Microsoft C++ derleyicisi ile birlikte kullanabilirsiniz. Visual Studio IDE 'yi, uzak Linux makineleri, MinGW-W64 ve Linux için Windows alt sistemi gibi UNIX ortamlarında GCC veya Clang ile de kullanabilirsiniz. C++ ' ı Visual Studio 'da kullanmak için C++ iş yüküyle **masaüstü geliştirme** 'nın yüklü olması gerekir. İş yükünü yüklemek veya isteğe bağlı bileşenleri eklemek veya kaldırmak için Visual Studio Yükleyicisi açın. Ayrıca, uzak bir Linux makinesini hedefliyorsanız, C++ iş yüküyle **Linux geliştirmeyi** de yükleyebilirsiniz. Android veya iOS geliştirmesi için, C++ iş yüküyle **mobil geliştirme** 'yi yükler.

## <a name="getting-started-on-the-command-line"></a>Komut satırına Başlarken

Bir UNIX komut satırı ortamı kullanacak şekilde, komut satırından Microsoft C++ derleyicisini kullanabilirsiniz. Komut isteminden, komut satırı C ve C++ derleyicisi (CL.EXE), bağlayıcı (LINK.EXE) ve diğer araçları (UNIX Make 'in Microsoft sürümü) ile NMAKE.EXE birlikte kullanarak derleyebilirsiniz.

UNIX 'te komutlar,/usr/bingibi ortak bir klasöre yüklenir. Visual Studio 'da, komut satırı araçları VC\bin alt dizinindeki ve alt dizinlerinde Visual Studio yükleme dizinine yüklenir. UNIX 'ten farklı olarak, bu araçlar düz bir komut istemi penceresinde kullanılamaz. Komut satırı araçlarını kullanmak için, C++ programlarını derlemek için gereken yolu ve diğer ortam değişkenlerini ayarlayan özel bir geliştirici komut istemi kullanmanız gerekir. Daha fazla bilgi için bkz. komut satırında [C/C++ kodu oluşturma](../build/building-on-the-command-line.md) ve [Izlenecek yol: komut satırında yerel C++ programı](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)derleme.

## <a name="debugging-your-code"></a>Kodunuzda hata ayıklama

Microsoft C++ projeleri için Visual Studio hata ayıklayıcısını, komut satırından veya IDE içinden kullanabilirsiniz. Kaynaklardaki adımlamayı etkinleştirmek için [/Z7,/Zi,/ZI (hata ayıklama bilgileri biçimi)](../build/reference/z7-zi-zi-debug-information-format.md) anahtarıyla derleyin. Daha fazla bilgi için bkz. [yerel kodda hata ayıklama](/visualstudio/debugger/debugging-native-code) ve [C++ masaüstü geliştirme IÇIN Visual Studio IDE 'yi kullanma](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).

GCC veya Clang ile derlenen programlar için, Visual Studio GDB 'yi, LLDB 'yi veya belirttiğiniz özel hata ayıklayıcıyı çağırır.

## <a name="visual-studio-project-system"></a>Visual Studio proje sistemi

Visual Studio proje sistemine MSBuild adı verilir. Proje dosyalarını XML biçiminde kullanır; C++ proje dosyaları. vcxproj uzantısına sahiptir. Birden çok kitaplık ve yürütülebilirden oluşan, her biri farklı bir derleyici seçenekleri kümesiyle veya farklı bir dilde oluşturulmuş olan bir uygulama, tek bir *çözümün* parçası olan birden çok projede depolanır. Çözüm, bir kapsayıcının birden çok projeyi birlikte gruplamak için soyutlamadır. Çözümler hakkında bilgi. sln uzantılı bir çözüm dosyasında depolanır. Daha fazla bilgi için bkz. [Visual Studio 'Da çözümler ve projeler](/visualstudio/ide/solutions-and-projects-in-visual-studio) ve [C++ masaüstü geliştirmesi IÇIN Visual Studio IDE 'yi kullanma](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).   >    >  Kullanılabilir Visual Studio proje şablonlarını görmek için ana menüden dosya yeni **Proje** ' yi seçin.

Visual Studio 2017 ' den başlayarak, CMake projelerine yönelik destek eklendi ve Microsoft C++ derleyicisini herhangi bir rastgele derleme sistemiyle veya bir kaynak dosya ve proje dosyası olmayan bir klasör ile kullanma seçenekleri eklenmiştir. Daha fazla bilgi için bkz. Visual Studio ['Da CMake projeleri](../build/cmake-projects-in-visual-studio.md) ve [Visual Studio 'Da klasör projelerini açma](../build/open-folder-projects-cpp.md).

## <a name="microsoft-specific-modifiers"></a>Microsoft'a özgü değiştiriciler

Microsoft C++ derleyicisi, Windows işletim sistemlerine yönelik programlamayı desteklemek için standart C++ programlama diline birkaç uzantı uygular. Bu uzantılar depolama sınıfı özniteliklerini, işlev çağırma kurallarını ve temel adresleme 'yi diğer şeyler arasında belirtmek için kullanılır. Desteklenen tüm C++ uzantılarının tam listesi için bkz. [Microsoft 'A özgü değiştiriciler](../cpp/microsoft-specific-modifiers.md).

C++ için Microsoft 'a özgü tüm uzantıları derleyici seçeneğini kullanarak devre dışı bırakabilirsiniz `/Za` . Birden çok platformda çalıştırmak üzere kod yazmak istiyorsanız bu seçenek önerilir. Derleyici seçeneği hakkında daha fazla bilgi için `/Za` bkz. [/za,/Ze (dil uzantılarını devre dışı bırak)](../build/reference/za-ze-disable-language-extensions.md). C++ derleyicisi uygunluğu hakkında daha fazla bilgi için bkz. [Microsoft C++ dil uygunluğu tablosu](../overview/visual-cpp-language-conformance.md) ve [Standart olmayan davranış](../cpp/nonstandard-behavior.md).

## <a name="precompiled-headers"></a>Önceden derlenmiş üstbilgiler

Microsoft C ve C++ derleyicileri, satır içi kod dahil olmak üzere herhangi bir C veya C++ kodunu önceden derlemeye yönelik seçenekler sağlar. Bu performans özelliğini kullanarak kodun kararlı bir gövdesini derleyebilir, kodun derlenmiş durumunu bir dosyada saklayabilir ve sonraki derlemeler sırasında, önceden derlenmiş kodu, hala geliştirme aşamasında olan kodla birleştirebilirsiniz. Kararlı kodun yeniden derlenmesi gerekmediğinden, sonraki her derleme daha hızlıdır.

Varsayılan olarak, tüm önceden derlenmiş kod, *pch. h* ve *pch. cpp* dosyalarında belirtilmiştir (Visual Studio 2017 ve önceki sürümlerde *stdadfx. h* ve *stdadfx. cpp* ). Önceden derlenmiş üstbilgiler hakkında daha fazla bilgi için bkz. [önceden derlenmiş üst bilgi dosyaları oluşturma](../build/creating-precompiled-header-files.md).

## <a name="related-sections"></a>İlgili bölümler

Daha fazla bilgi için bkz. [Windows 'Da Linux programlarını çalıştırma](../porting/porting-from-unix-to-win32.md).

## <a name="see-also"></a>Ayrıca bkz.

[Projeler ve derleme sistemleri](../build/projects-and-build-systems-cpp.md)
