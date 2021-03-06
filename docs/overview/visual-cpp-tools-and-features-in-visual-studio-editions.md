---
description: 'Daha fazla bilgi edinin: Visual Studio sürümlerindeki C++ araçları ve özellikleri'
title: Visual Studio Sürümlerinde C++ Araçları ve Özellikleri
ms.date: 05/21/2019
helpviewer_keywords:
- tools and platforms [C++]
ms.assetid: 3d88607b-9cc4-490a-8d4c-31ee7610a26f
ms.openlocfilehash: 6253e52fa300cc60de4b2700b384fde6f5ffe1ee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254631"
---
# <a name="c-tools-and-features-in-visual-studio-editions"></a>Visual Studio Sürümlerinde C++ Araçları ve Özellikleri

::: moniker range=">=msvc-160"

Aşağıdaki C++ özellikleri Visual Studio 2019 ' de mevcuttur. Aksi belirtilmedikçe tüm özellikler tüm sürümlerde kullanılabilir: Visual Studio Community, Visual Studio Professional ve Visual Studio Enterprise. Bazı özellikler, Visual Studio Yükleyicisi ile yükleyebileceğiniz belirli iş yükleri veya isteğe bağlı bileşenler gerektirir.

## <a name="platforms"></a>Platformlar

- Windows Masaüstü
- Evrensel Windows Platformu ((tablet, PC, Xbox, IoT ve HoloLens))
- Linux
- Android
- iOS

## <a name="compilers"></a>Derleyicileri

- X86, x64, ARM ve ARM64 için MSVC 32 bit derleyicisi
- X86, x64, ARM ve ARM64 için MSVC 64 bit derleyicisi
- ARM için GCC çapraz derleyicisi
- Clang/LLVM
  - Windows, Clang/LLVM 7,0, x86 veya x64 'u hedefliyor (yalnızca CMake desteği). Diğer Clang sürümleri çalışabilir ancak resmi olarak desteklenmeyebilir.
  - Linux 'ta, disin tarafından desteklenen tüm Clang/LLVM yüklemeleri.

## <a name="c-workloads"></a>C++ Iş yükleri

Visual Studio, C++ geliştirmesi için aşağıdaki iş yüklerini içerir. Bunlardan herhangi birini veya tümünü, .NET masaüstü geliştirme, Python geliştirme, Azure geliştirme, Visual Studio uzantısı geliştirme ve diğer iş yükleriyle birlikte yükleyebilirsiniz.

### <a name="desktop-development-with-c"></a>C++ ile masaüstü geliştirme

Verilen

- C++ temel masaüstü özellikleri

İsteğe bağlı bileşenler:

- MSVC v142-VS 2019 C++ x64/x86 derleme araçları (v 14.21)
- Windows 10 SDK (10.0.17763.0)
- Tam zamanında hata ayıklayıcı
- C++ profil oluşturma araçları
- Windows için C++ CMake araçları
- V142 derleme araçları için C++ ATL (x86 & x64)
- Boost. test için test bağdaştırıcısı
- Google Test için Test Bağdaştırıcısı
- Live Share
- IntelliCode
- IntelliTrace (yalnızca Kurumsal)
- V142 derleme araçları için C++ MFC (x86 & x64)
- V142 derleme araçları için C++/CLı desteği (14,21)
- V142 derleme araçları için C++ modülleri (x64/x86 – deneysel)
- Windows için Clang derleyicisi
- IncrediBuild-derleme hızlandırma
- Windows 10 SDK (10.0.17134.0)
- Windows 10 SDK (10.0.16299.0)
- MSVC v141-VS 2017 C++ x64/x86 derleme araçları (v 14.16)
- MSVC v140-VS 2015 C++ derleme araçları (v 14.00)

### <a name="linux-development-with-c"></a>C++ ile Linux geliştirme

Verilen

- C++ temel özellikleri
- Windows Universal C çalışma zamanı
- Linux geliştirme için C++

İsteğe bağlı bileşenler:

- Linux için C++ CMake araçları
- Katıştırılmış ve IoT geliştirme araçları

### <a name="universal-windows-platform-development"></a>Evrensel Windows Platformu geliştirme

Verilen

- Visual Studio için Blend
- .NET Native ve .NET Standard
- NuGet Paket Yöneticisi
- Evrensel Windows Platformu araçları
- Windows 10 SDK (10.0.17763.0)

İsteğe bağlı bileşenler:

- IntelliCode
- IntelliTrace (yalnızca Kurumsal)
- USB cihaz bağlantısı
- C++ (v142) Evrensel Windows Platformu araçları
- C++ (v141) Evrensel Windows Platformu araçları
- DirectX için grafik hata ayıklayıcı ve GPU Profiler
- Windows 10 SDK (10.0.18362.0)
- Windows 10 SDK (10.0.17134.0)
- Windows 10 SDK (10.0.16299.0)
- Mimari ve analiz araçları

### <a name="c-game-development"></a>C++ oyun geliştirme

Verilen

- C++ temel özellikleri
- Windows Universal C çalışma zamanı
- C++ 2019 yeniden dağıtılabilir güncelleştirmesi
- MSVC v142-VS 2019 C++ x64/x86 derleme araçları (v 14.21)

İsteğe bağlı bileşenler:

- C++ profil oluşturma araçları
- Windows 10 SDK (10.0.17763.0)
- IntelliCode
- IntelliTrace (yalnızca Kurumsal)
- Windows 10 SDK (10.0.17134.0)
- Windows 10 SDK (10.0.16299.0)
- IncrediBuild-derleme hızlandırma
- Cocos
- Unreal Engine yükleyicisi
- Unreal Engine için Android IDE desteği

### <a name="mobile-development-with-c"></a>C++ ile mobil geliştirme

Verilen

- C++ temel özellikleri
- Android SDK kurulumu (API düzeyi 25) (C++ ile mobil geliştirme için yerel yükleme)

İsteğe bağlı bileşenler:

- Android NDK (R16B)
- Apache Ant (1.9.3)
- C++ Android geliştirme araçları
- IntelliCode
- Google Android Emulator (API düzeyi 25) (yerel yüklemesi)
- Intel Hardware Accelerated Execution Manager (HAXM) (yerel yüklemesi)
- Android NDK (R16B) (32 bit)
- C++ iOS geliştirme araçları
- IncrediBuild-derleme hızlandırma

## <a name="individual-components"></a>Bireysel bileşenler

Bu bileşenleri herhangi bir iş yüküyle bağımsız olarak yükleyebilirsiniz.

- JavaScript tanılama
- Live Share
- V142 derleme araçları için C++ Evrensel Windows Platformu çalışma zamanı
- ClickOnce yayımlama
- Microsoft Visual Studio Installer projeleri

## <a name="libraries-and-headers"></a>Kitaplıklar ve üstbilgiler

- Windows üstbilgileri ve kitaplıkları
- Windows Universal C çalışma zamanı (CRT)
- C++ Standart Kitaplığı
- ATL
- MFC
- .NET Framework sınıf kitaplığı
- .NET için C++ destek kitaplığı
- OpenMP 2,0
- Vcpkg Kataloğu aracılığıyla 900 üzerinde açık kaynak kitaplığı

## <a name="build-and-project-systems"></a>Derleme ve proje sistemleri

- CMake
- Açık klasör aracılığıyla tüm derleme sistemleri
- Komut satırı derlemeleri (msbuild.exe)
- Yerel çoklu hedefleme
- Yönetilen çoklu sürüm
- Paralel derlemeler
- Yapı özelleştirmeleri
- Özellik sayfaları genişletilebilirliği

## <a name="project-templates"></a>Proje şablonları

Aşağıdaki proje şablonları, yüklediğiniz iş yüklerine bağlı olarak kullanılabilir.

Windows Masaüstü:

- Boş Proje
- Konsol uygulaması
- Windows Masaüstü Sihirbazı
- Windows masaüstü uygulaması
- Paylaşılan öğeler projesi
- MFC uygulaması
- Dinamik bağlantı kitaplığı
- CLR boş proje
- CLR Konsol uygulaması
- Statik kitaplık
- CMake projesi
- ATL projesi
- MFC dinamik bağlantı kitaplığı
- CLR sınıf kitaplığı
- Makefile projesi (Windows)
- MFC ActiveXControl
- Yerel birim testi projesi
- Google Test

Evrensel Windows Platformu (C++/CX):

- Boş Uygulama
- DirectX 11 ve XAML uygulaması
- DirectX 11 uygulaması
- DirectX 12 uygulaması
- Birim test uygulaması
- DLL
- Windows Çalışma Zamanı Bileşeni
- Statik kitaplık
-  Windows Uygulaması Paketleme Projesi

Linux:

- Konsol uygulaması (Linux)
- Boş proje (Linux)
- Raspberry Pi yanıp sönme
- Makefile projesi (Linux)

## <a name="tools"></a>Araçlar

- Artımlı bağlayıcı (Link.exe)
- Microsoft makefile yardımcı programı (Nmake.exe)
- LIB Generator (Lib.exe)
- Windows Kaynak derleyicisi (Rc.exe)
- Windows kaynaktan nesne dönüştürücüsüne (CvtRes.exe)
- Tarama bilgileri bakım yardımcı programı (BscMake.exe)
- C++ ad dekoratör (Undname.exe)
- COFF/PE Dumper (Dumpbin.exe)
- COFF/PE Düzenleyicisi (Editbin.exe)
- MASA (Ml.exe)
- Spy++
- ErrLook
- AtlTrace
- Çıkarsama Kuralları
- Profil temelli Iyileştirmeler

## <a name="debugging-features"></a>Hata ayıklama özellikleri

- Yerel hata ayıklama
- Natvis (yerel tür görselleştirme)
- Grafik hata ayıklaması
- Yönetilen hata ayıklama
- GPU kullanımı
- Bellek kullanımı
- Uzaktan Hata Ayıklama
- SQL hata ayıklaması
- Statik kod analizi

## <a name="designers-and-editors"></a>Tasarımcılar ve düzenleyiciler

- XAML Tasarımcısı
- CSS stil Tasarımcısı/Düzenleyicisi
- HTML Tasarımcısı/Düzenleyicisi
- XML Düzenleyicisi
-  Kaynak Kod Düzenleyici
- Üretkenlik özellikleri: yeniden düzenleme, EDG IntelliSense altyapısı, C++ kod biçimlendirme
- Windows Form Tasarımcısı
- Veri Tasarımcısı
- Yerel kaynak Düzenleyicisi (. RC dosyaları)
- Kaynak Düzenleyicileri
- Model düzenleyicisi
- Gölgelendirici tasarımcısı
- Canlı bağımlılık doğrulaması (yalnızca Kurumsal)
- Mimari katman diyagramları (yalnızca Kurumsal)
- Mimari doğrulaması (yalnızca Kurumsal)
- Kod kopyası (yalnızca Kurumsal)

## <a name="data-features"></a>Veri özellikleri

- Veri Tasarımcısı
- Veri nesneleri
- Web Hizmetleri
- Sunucu Gezgini

## <a name="automation-and-extensibility"></a>Otomasyon ve genişletilebilirlik

- Genişletilebilirlik nesne modelleri
- Kod modeli
- Proje Modeli
- Kaynak Düzenleyicisi modeli
- Sihirbaz modeli
- Hata ayıklayıcı nesne modeli

## <a name="application-lifecycle-management-tools"></a>Uygulama yaşam döngüsü yönetimi araçları

- Birim testi (Microsoft yerel C++, Boost. test, Google Test, CTest)
- Kod Haritası ve bağımlılık grafikleri (Professional ve Enterprise)
- Kod kapsamı (yalnızca Kurumsal)
- El ile test (yalnızca Kurumsal)
- Keşif testi (yalnızca Kurumsal)
- Test çalışması yönetimi (yalnızca Kurumsal)
- Kod Haritası hata ayıklayıcısı tümleştirmesi (yalnızca Kurumsal)
- Live Unit Testing (yalnızca Kurumsal)
- IntelliTrace (yalnızca Kurumsal)
- IntelliTest (yalnızca Kurumsal)
- Microsoft Fakes (birim testi yalıtımı) (yalnızca Kurumsal)
- Kod kapsamı (yalnızca Kurumsal)

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio'yu yükleme](/visualstudio/install/install-visual-studio)<br/>
[Visual Studio 'daki yenilikler](/visualstudio/ide/whats-new-in-visual-studio)<br/>
[Visual Studio 'da C++ proje türleri](../build/reference/visual-cpp-project-types.md)

::: moniker-end

::: moniker range="<=msvc-150"

Aşağıdaki tablolarda, Visual Studio 2017 ' de bulunan Visual C++ özellikleri gösterilmektedir. Hücredeki bir X, özelliğin kullanılabildiğini belirtir; boş bir hücre, özelliğin kullanılabilir olmadığını gösterir. Parantez içindeki notlar bir özelliğin kullanılabildiğini, ancak kısıtlı olduğunu gösterir.

## <a name="platforms"></a>Platformlar

|Platform|Windows 10 için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Visual Studio Community/Professional|Visual Studio Enterprise|
|-|-|-|-|-|
|Windows Masaüstü||X|X|X|
|Evrensel Windows Platformu ((Phone, tablet, PC, Xbox, IoT ve HoloLens))|X||X|X|
|Linux|X|X|
|Microsoft Store 8,1|||X|X|
|Windows Phone 8.0|||X|X|
|Android|||X|X|
|iOS|||X|X|

## <a name="compilers"></a>Derleyicileri

|Derleyici|Windows için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Visual Studio Professional/topluluk|Visual Studio Enterprise|
|--------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|MSVC 32-bit x86 derleyicisi|X|X|X|X|
|X86_arm çapraz derleyici|X||X|X|
|MSVC 64-bit x64 derleyicisi|||X|X|
|X86_ x64 çapraz derleyicisi|X|X|X|X|

## <a name="libraries-and-headers"></a>Kitaplıklar ve üstbilgiler

|Kitaplık veya üst bilgi|Windows için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Visual Studio Professional/topluluk|Visual Studio Enterprise|
|-----------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Windows üstbilgileri ve kitaplıkları ve CRT kitaplığı|Sayı|X|X|X|
|C++ Standart Kitaplığı|X|X|X|X|
|ATL|||X|X|
|MFC|||X|X|
|.NET Framework sınıf kitaplığı||X|X|X|
|.NET için C++ destek kitaplığı||X|X|X|
|OpenMP 2,0|X|X|X|X|

## <a name="project-templates"></a>Proje şablonları

|Şablon|Windows için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Visual Studio Professional/topluluk|Visual Studio Enterprise|
|--------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|UWP, Windows 8.1 Windows Phone 8,0 için XAML şablonları|X||X|X|
|Direct3D Uygulaması|X||X|X|
|DLL (Evrensel Windows)|X||X|X|
|Statik kitaplık (Evrensel Windows)|X||X|X|
|Windows Çalışma Zamanı Bileşeni|X||X|X|
|Birim testi uygulaması (Evrensel Windows)|X||X|X|
|ATL projesi|||X|X|
|Sınıf kitaplığı (CLR)||X|X|X|
|CLR Konsol uygulaması||X|X|X|
|CLR boş proje||X|X|X|
|Özel Sihirbaz|||X|X|
|Boş Proje||X|X|X|
|Makefile projesi||X|X|X|
|MFC ActiveX denetimi|||X|X|
|MFC uygulaması|||X|X|
|MFC DLL|||X|X|
|Test projesi|X|X|X|X|
|Win32 konsol uygulaması||X|X|X|
|Win32 projesi||X|X|X|

## <a name="tools"></a>Araçlar

|Araç|Windows için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Visual Studio Professional/topluluk|Visual Studio Enterprise|
|----------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Artımlı bağlayıcı (Link.exe)|X|X|X|X|
|Program bakım yardımcı programı (Nmake.exe)||X|X|X|
|LIB Generator (Lib.exe)|X|X|X|X|
|Windows Kaynak derleyicisi (Rc.exe)|X|X|X|X|
|Windows kaynaktan nesne dönüştürücüsüne (CvtRes.exe)||X|X|X|
|Tarama bilgileri bakım yardımcı programı (BscMake.exe)|X|X|X|X|
|C++ ad dekoratör (Undname.exe)|X|X|X|X|
|COFF/PE Dumper (Dumpbin.exe)|X|X|X|X|
|COFF/PE Düzenleyicisi (Editbin.exe)|X|X|X|X|
|MASA (Ml.exe)|||X|X|
|Spy++|||X|X|
|ErrLook|||X|X|
|AtlTrace|||X|X|
|Devenv.com|||X|X|
|Çıkarsama Kuralları|||X|X|
|VCBuild. vcproj projelerini MSBuild 'e yükselt (VCUpgrade.exe)|X|X|X|X|
|Profil temelli Iyileştirmeler|||X|X|

## <a name="debugging-features"></a>Hata ayıklama özellikleri

|Hata ayıklama özelliği|Windows için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Visual Studio Professional/topluluk|Visual Studio Enterprise|
|-----------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Yerel hata ayıklama|X|X|X|X|
|Natvis (yerel tür görselleştirme)|X|X|X|X|
|Grafik hata ayıklaması|X||X|X|
|Yönetilen hata ayıklama||X|X|X|
|GPU kullanımı|X||X|X|
|Bellek kullanımı|X||X|X|
|Uzaktan Hata Ayıklama|X|X|X|X|
|SQL hata ayıklaması|||X|X|
|Statik kod analizi|Sınırlı|Sınırlı|X|X|

## <a name="designers-and-editors"></a>Tasarımcılar ve düzenleyiciler

|Tasarımcı veya düzenleyici|Windows için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Visual Studio Professional/topluluk|Visual Studio Enterprise|
|------------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|XAML Tasarımcısı|X||X|X|
|CSS stil Tasarımcısı/Düzenleyicisi|X|X|X|X|
|HTML Tasarımcısı/Düzenleyicisi|X|X|X|X|
|XML Düzenleyicisi|X|X|X|X|
| Kaynak Kod Düzenleyici|X|X|X|X|
|Üretkenlik özellikleri: yeniden düzenleme, IntelliSense, C++ kod biçimlendirme|X|X|X|X|
|Windows Form Tasarımcısı||X|X|X|
|Veri Tasarımcısı|||X|X|
|Yerel kaynak Düzenleyicisi (. RC dosyaları)|||X|X|
|Kaynak Düzenleyicileri|X|X|X|X|
|Model düzenleyicisi|X||X|X|
|Gölgelendirici tasarımcısı|X||X|X|

## <a name="data-features"></a>Veri özellikleri

|Veri özelliği|Windows için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Visual Studio Professional/topluluk|Visual Studio Enterprise|
|------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Veri Tasarımcısı|||X|X|
|Veri nesneleri|||X|X|
|Web Hizmetleri|||X|X|
|Sunucu Gezgini|||X|X|

## <a name="build-and-project-systems"></a>Derleme ve proje sistemleri

|Yapı veya proje özelliği|Windows için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Visual Studio Professional/topluluk|Visual Studio Enterprise|
|------------------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Komut satırı derlemeleri (msbuild.exe)|X|X|X|X|
|Yerel çoklu hedefleme||X|X|X|
|Yönetilen çoklu sürüm||X|X|X|
|Paralel derlemeler|X|X|X|X|
|Yapı özelleştirmeleri|X|X|X|X|
|Özellik sayfaları genişletilebilirliği|X|X|X|X|

## <a name="automation-and-extensibility"></a>Otomasyon ve genişletilebilirlik

|Otomasyon ve genişletilebilirlik|Windows için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Visual Studio Professional/topluluk|Visual Studio Enterprise|
|----------------------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Genişletilebilirlik nesne modelleri|||X|X|
|Kod modeli|||X|X|
|Proje Modeli|||X|X|
|Kaynak Düzenleyicisi modeli|||X|X|
|Sihirbaz modeli|||X|X|
|Hata ayıklayıcı nesne modeli|||X|X|

## <a name="application-lifecycle-management-tools"></a>Uygulama yaşam döngüsü yönetimi araçları

|Araç|Windows için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Visual Studio Professional/topluluk|Visual Studio Enterprise|
|-|-|-|-|-|
|Birim testi (yerel çerçeve)|X|X|X|X|
|Birim testi (yönetilen çerçeve)||X|X|X|
|Kod kapsamı||||X|
|El ile test||||X|
|Keşif testi||||X|
|Test çalıştırması yönetimi||||X|
|Kod Haritası ve bağımlılık grafikleri|||salt okunur|X|
|Kod Haritası hata ayıklaması||||X|

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio'yu yükleme](/visualstudio/install/install-visual-studio)<br/>
[Visual Studio 'daki yenilikler](/visualstudio/ide/whats-new-in-visual-studio)<br/>
[Visual Studio 'da C++ proje türleri](../build/reference/visual-cpp-project-types.md)

::: moniker-end
