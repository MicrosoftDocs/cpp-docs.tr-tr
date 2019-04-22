---
title: C/C++ projeleri ve Visual Studio'da derleme sistemleri
ms.description: Use Visual Studio to compile and build C++ projects for Windows, ARM or Linux based on any project system.
ms.date: 12/08/2018
f1_keywords:
- vcbuilding
- buildingaprogramVC
helpviewer_keywords:
- builds [C++]
- Visual C++ projects, building
- projects [C++], building
- builds [C++], options
- Visual C++, build options
ms.assetid: fa6ed4ff-334a-4d99-b5e2-a1f83d2b3008
ms.openlocfilehash: 6a4048d741cf291d8d6173c1444b6933523c6851
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58775432"
---
# <a name="cc-projects-and-build-systems-in-visual-studio"></a>C/C++ projeleri ve Visual Studio'da derleme sistemleri

Visual Studio 2017, düzenleme, derleme ve herhangi bir C++ kod tam IntelliSense desteği ile temel bir Visual Studio Proje veya derleme MSVC araç takımı ile kod dönüştürmek zorunda kalmadan oluşturmak için kullanabilirsiniz. Örneğin, bir Windows makinede platformlar arası CMake projesini Visual Studio'da Düzenle ardından g ++ uzak Linux makinesinde kullanarak Linux için derleyin.

## <a name="c-compilation"></a>C++ derleme

İçin *derleme* bir veya daha fazla dosyalardan kaynak kodu derleyin ve ardından bu dosyalar bir yürütülebilir dosya (.exe), dinamik yük kitaplığı (.dll) veya bir statik kitaplık (.lib) bağlamak bir C++ programını anlamına gelir. 

Temel C++ derleme üç ana adımdan oluşur:

- C++ önişlemcisi, her kaynak dosyasındaki tüm #directives ve makro tanımlarını dönüştürür. Bu, oluşturur bir *çeviri birimi*.
- C++ derleyicisi, derleyici seçenekleri kümesi uygulayarak her çeviri birimini nesne (.obj) dosyalarına derlenir.
- *Bağlayıcı* nesne dosyaları ayarlanan bağlayıcı seçenekleri uygulayarak bir tek yürütülebilir dosya birleştirir. 

## <a name="the-msvc-toolset"></a>MSVC araç takımı

Microsoft C++ Derleyici, bağlayıcı, standart kitaplıkları ve ilgili hizmet programları (bir araç zincirinizi veya "derleme Araçları" olarak da bilinir) MSCV derleyici araç takımı oluşturur. Bu, Visual Studio'da dahil edilir. Ayrıca indirin ve araç takımı tek başına paket olarak ücretsiz kullanmak [Visual Studio 2017 için derleme araçları indirme konumu](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2017).

MSVC derleyicisi (cl.exe) doğrudan komut satırından çağırarak basit programlar oluşturabilirsiniz. Aşağıdaki komut, bir tek bir kaynak kodu dosyasını kabul eder ve adlı yürütülebilir bir dosya oluşturmak için cl.exe çağırır *hello.exe*: 

```cmd
cl /EHsc hello.cpp
```
Unutmayın, burada ' % s'derleyicisi (cl.exe) son çıktı dosyası üretmek için C++ önişlemcisi ve bağlayıcı otomatik olarak çağırır.  Daha fazla bilgi için [komut satırında derleme](building-on-the-command-line.md).

## <a name="build-systems-and-projects"></a>Sistemler ve projeler oluşturun

Çoğu gerçek program bazı tür kullanın *yapı sistemi* birden fazla yapılandırması için birden çok kaynak dosyalarını derlerken, karmaşıklık yönetmek için (yani debug release), birden çok Platformu (x86, x64, ARM, vb.), özel derleme adımlar ve belirli bir sırayla derlenmelidir bile yürütülebilir. Bir yapı yapılandırma dosyasında ayarları yapın ve onu çağırmak önce derleyici derleme sistemi, dosya giriş olarak kabul eder. Kaynak kodu dosyaları ve yürütülebilir bir dosya oluşturmak için gereken yapı yapılandırma dosyaları kümesini adlı bir *proje*. 

Aşağıdaki listede C++ - Visual Studio projeleri için çeşitli seçenekler gösterilmektedir:

- Visual Studio IDE kullanarak bir Visual Studio projesi oluşturun ve özellik sayfaları kullanarak yapılandırın. Visual Studio projeleri, Windows üzerinde çalışan programlar üretir. Genel bakış için bkz. [derleme ve oluşturma](/visualstudio/ide/compiling-and-building-in-visual-studio) Visual Studio belgelerinde.

- CMakeLists.txt dosyasını içeren klasörü açın. CMake desteği, Visual Studio'da tümleşiktir. Düzenlemek için test ve herhangi bir şekilde CMake dosyalarda değişiklik yapmadan hata ayıklama için IDE kullanabilirsiniz. Bu, farklı düzenleyici kullanan aynı CMake proje içinde diğer olarak çalışmanıza olanak sağlar. CMake, platformlar arası geliştirme için önerilen yaklaşımdır. Daha fazla bilgi için [CMake projelerini](cmake-projects-in-visual-studio.md).
 
- gevşek bir kaynak dosya klasörü hiçbir proje dosyasını açın. Visual Studio, dosyaları oluşturmak için buluşsal yöntemler kullanır. Bu, derlemek ve küçük konsol uygulamaları çalıştırmak için kolay bir yoludur. Daha fazla bilgi için [Klasör Aç, projeler](open-folder-projects-cpp.md).

- derleme görevleri dosyası ya da herhangi diğer yapı sistemini yapılandırma dosyasını içeren klasörü açın. JSON dosyaları klasöre ekleyerek herhangi bir rastgele derleme komut çağırmak için Visual Studio yapılandırabilirsiniz. Daha fazla bilgi için [Klasör Aç, projeler](open-folder-projects-cpp.md).
 
- Windows derleme görevleri dosyası, Visual Studio'da açın. Daha fazla bilgi için [NMAKE başvurusu](reference/nmake-reference.md).

## <a name="msbuild-from-the-command-line"></a>Komut satırında MSBuild 

MSBuild komut satırı seçenekleri ile birlikte bir .vcxproj dosyası geçirerek, komut satırından çalıştırabilirsiniz. Bu yaklaşım, MSBuild iyi bir anlayış gerektirir ve yalnızca gerçekten gerekli olduğunda önerilir. Daha fazla bilgi için [MSBuild](msbuild-visual-cpp.md).

## <a name="in-this-section"></a>Bu Bölümde

[Visual Studio projeleri](creating-and-managing-visual-cpp-projects.md) nasıl oluşturmak, yapılandırmak ve C++ derleme için kendi yerel kullanarak Visual Studio projelerinde yapı sistemi (MSBuild).

[CMake projelerini](cmake-projects-in-visual-studio.md) nasıl kod, derleme ve Visual Studio'da CMake projelerini dağıtın.

[Açık klasör projelere](open-folder-projects-cpp.md) kod, derleme ve dağıtma C++ projeleri için Visual Studio kullanmayı bağlı herhangi bir rastgele yapı sistemini veya hiçbir derleme sistemi. Asla. 

[Yayın derlemeleri](release-builds.md) son kullanıcıların dağıtımını oluşturun ve en iyi duruma getirilmiş sürüm ilgili sorunları giderme oluşturur.

[Komut satırından MSVC araç takımını kullanma](building-on-the-command-line.md)<br/>
C/C++ derleyicisi ve derleme araçlarını doğrudan Visual Studio IDE kullanarak yerine komut satırını nasıl kullanılacağını açıklar.

[Visual Studio'da DLL'leri oluşturma](dlls-in-visual-cpp.md) oluşturma, hata ayıklayın ve Visual Studio'da C/C++ DLL'leri (paylaşılan kitaplıklar) dağıtın.

[İzlenecek yol: Statik kitaplık oluşturma ve kullanma](walkthrough-creating-and-using-a-static-library-cpp.md) .lib ikili dosyasının nasıl oluşturulacağı.

[C/C++ yalıtılmış uygulamaları ve yan yana derlemeleri oluşturma](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md) yalıtılmış uygulamalar ve yan yana derlemeler fikrini tabanlı Windows Masaüstü uygulamalar için dağıtım modelini açıklar.

[C++ projeleri için 64 bit x64 yapılandırma hedefleri](configuring-programs-for-64-bit-visual-cpp.md) nasıl 64-bit x64 hedefine MSVC donanımla derleme araçları.

[C++ projeleri ARM işlemcileri için yapılandırma](configuring-programs-for-arm-processors-visual-cpp.md) nasıl MSVC derleme araçları, ARM donanım hedeflemek için kullanın.

[Kodunuzu iyileştirme](optimizing-your-code.md) destekli program iyileştirmeleri gibi çeşitli yollarla kodunuzda en iyi duruma getirme.

[Programları Windows XP için yapılandırma](configuring-programs-for-windows-xp.md) hedef Windows XP MSVC derleme araçlarını nasıl.

[C/C++ Derleme Başvurusu](reference/c-cpp-building-reference.md)<br/>
C++, derleyici ve bağlayıcı seçenekleri ve çeşitli derleme araçları oluşturmaya programı hakkında başvuru makalelerimize bağlantılar sağlar.
