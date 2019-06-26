---
title: Visual Studio Sürümlerinde C++ Araçları ve Özellikleri
ms.date: 05/21/2019
helpviewer_keywords:
- tools and platforms [C++]
ms.assetid: 3d88607b-9cc4-490a-8d4c-31ee7610a26f
ms.openlocfilehash: a7514e5cc52b24740b82cc067e77955c4784c9f0
ms.sourcegitcommit: 8bb2bea1384b290b7570b01608a86c7488ae7a02
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2019
ms.locfileid: "67400636"
---
# <a name="c-tools-and-features-in-visual-studio-editions"></a>Visual Studio Sürümlerinde C++ Araçları ve Özellikleri


::: moniker range=">=vs-2019"


Aşağıdaki C++ özellikleri Visual Studio 2019 içinde kullanılabilir. Aksi belirtilmedikçe, tüm özellikleri tüm sürümlerinde kullanılabilir: Visual Studio Community, Visual Studio Professional ve Visual Studio Enterprise. Bazı özellikler, belirli iş yükleri veya isteğe bağlı bileşenler, Visual Studio Yükleyicisi ile yükleyebilirsiniz gerektirir.

## <a name="platforms"></a>Platformlar

- Windows Masaüstü
- Evrensel Windows Platformu ((tablet, PC, Xbox, IOT ve HoloLens))
- Linux
- Android
- iOS

## <a name="compilers"></a>Derleyicileri

- MSVC x86, x 64, ARM ve ARM64 için 32-bit derleyici
- MSVC x86, x 64, ARM ve ARM64 için 64 bit derleyici
- GCC için ARM çapraz derleyici
- Clang/LLVM
  - X86 veya x64 (yalnızca CMake desteği) hedefleyen Windows üzerinde Clang/LLVM 7.0. Clang sürümlerinden çalışabilir ancak resmi olarak desteklenmez.
  - Linux üzerinde distro tarafından desteklenen herhangi bir Clang/LLVM yükleme.
 
## <a name="c-workloads"></a>C++İş yükleri

Visual Studio içeren aşağıdaki iş yükleri için C++ geliştirme. Bunlar, .NET masaüstü geliştirme, Python geliştirme, Azure geliştirme, Visual Studio uzantısı geliştirme ve diğerleri gibi diğer iş yüklerinin yanı sıra bir bölümünü veya tamamını yükleyebilirsiniz.

### <a name="desktop-development-with-c"></a>C++ ile masaüstü geliştirme

Dahil edilen:
- C++Temel masaüstü özellikleri

İsteğe bağlı bileşenler:
- MSVC v142 - VS 2019 C++ x64/x86 derleme araçlarını (v14.21)
- Windows 10 SDK (10.0.17763.0)
- Just-In-Time hata ayıklayıcı
- C++ profil oluşturma araçları
- Windows için C++ CMake araçları
- V142 derleme Araçları (x86 & x64) için C++ ATL
- Boost.Test için test bağdaştırıcısı
- Google Test için test bağdaştırıcısı
- Live Share
- IntelliCode
- IntelliTrace (yalnızca Kurumsal)
- V142 derleme Araçları (x86 & x64) için C++ MFC
- C++/ CLI v142 derleme Araçları (14.21) desteği
- C++ modülleri v142 için derleme Araçları (x64/x86 – Deneysel)
- Windows için clang derleyicisi
- IncrediBuild - derleme hızlandırma
- Windows 10 SDK (10.0.17134.0)
- Windows 10 SDK (10.0.16299.0)
- MSVC v141 - VS 2017 C++ x64/x86 derleme araçlarını (v14.16)
- MSVC v140 - VS 2015 C++ derleme Araçları (v14.00)

### <a name="linux-development-with-c"></a>C++ ile Linux geliştirme

Dahil edilen:
- C++ temel özellikler
- Windows Evrensel C çalışma zamanı
- C++ Linux geliştirme için

İsteğe bağlı bileşenler:
- Linux için C++ CMake araçları
- Katıştırılmış ve IOT geliştirme araçları

### <a name="universal-windows-platform-development"></a>Evrensel Windows platformu geliştirme

Dahil edilen:
- Visual Studio için Blend
- .NET native ve .NET Standard
- NuGet Paket Yöneticisi
- Evrensel Windows platformu araçları
- Windows 10 SDK (10.0.17763.0)

İsteğe bağlı bileşenler:
- IntelliCode
- IntelliTrace (yalnızca Kurumsal)
- USB cihaz bağlantısı
- (V142) C++ Evrensel Windows platformu araçları
- (V141) C++ Evrensel Windows platformu araçları
- DirectX için grafik hata ayıklayıcı ve GPU
- Windows 10 SDK (10.0.18362.0)
- Windows 10 SDK (10.0.17134.0)
- Windows 10 SDK (10.0.16299.0)
- Mimari ve analiz araçları

### <a name="c-game-development"></a>C++Oyun Geliştirme

Dahil edilen:
- C++ temel özellikler
- Windows Evrensel C çalışma zamanı
- C++ 2019 yeniden dağıtılabilir güncelleştirme
- MSVC v142 - VS 2019 C++ x64/x86 derleme araçlarını (v14.21)

İsteğe bağlı bileşenler:
- C++ profil oluşturma araçları
- Windows 10 SDK (10.0.17763.0)
- IntelliCode
- IntelliTrace (yalnızca Kurumsal)
- Windows 10 SDK (10.0.17134.0)
- Windows 10 SDK (10.0.16299.0)
- IncrediBuild - derleme hızlandırma
- Cocos
- Unreal Engine yükleyicisi
- Unreal engine için Android IDE desteği

### <a name="mobile-development-with-c"></a>C++ ile Mobil Geliştirme

Dahil edilen:
- C++ temel özellikler
- Android SDK kurulumu (API düzeyi 25) (C++ ile Mobil Geliştirme için yerel yükleme)

İsteğe bağlı bileşenler:
- Android NDK (R16B)
- Apache Ant (1.9.3)
- C++ Android geliştirici araçları
- IntelliCode
- Google Android Emulator (API düzeyi 25) (yerel kurulum)
- Intel donanım hızlandırılmış yürütme Yöneticisi (HAXM) (yerel kurulum)
- Android NDK (R16B) (32 bit)
- C++ iOS geliştirici araçları
- IncrediBuild - derleme hızlandırma


## <a name="individual-components"></a>Bağımsız bileşenler

Tüm iş yükünden bağımsız olarak, bu bileşenleri yükleyebilirsiniz.

- JavaScript tanılamaları
- Live Share
- C++ Evrensel Windows platformu çalışma zamanı için v142 derleme araçları
- ClickOnce yayımlama
- Microsoft Visual Studio yükleyici projeleri

## <a name="libraries-and-headers"></a>Kitaplıklar ve üstbilgiler

- Windows üstbilgiler ve kitaplıkları
- Windows Evrensel C çalışma zamanı (CRT)
- C++ Standart Kitaplığı
- ATL
- MFC
- .NET Framework sınıf kitaplığı
- .NET için C++ destek kitaplığı
- OpenMP 2.0
- Vcpkg Kataloğu aracılığıyla 900 açık kaynak kitaplıkları

## <a name="build-and-project-systems"></a>Derleme ve proje sistemleri

- CMake
- Herhangi bir derleme sistemi üzerinden klasörü aç
- Komut satırı yapıları (msbuild.exe)
- Yerel çoklu sürüm desteği
- Yönetilen çoklu sürüm desteği
- Paralel yapılar
- Derleme özelleştirmeleri
- Özellik sayfaları genişletilebilirliği

## <a name="project-templates"></a>Proje şablonları

Şu proje şablonlarını, yüklediğiniz hangi iş yüklerini bağlı olarak kullanılabilir.

Windows Masaüstü:
- Boş Proje
- Konsol uygulaması
- Windows Masaüstü Sihirbazı
- Windows masaüstü uygulaması
- Paylaşılan öğeler projesi
- MFC uygulaması
- Dinamik bağlantı kitaplığı
- CLR boş proje
- CLR konsol uygulaması
- Statik kitaplık
- CMake projesi
- ATL projesi
- MFC dinamik bağlantı kitaplığı
- CLR sınıf kitaplığı
- Derleme görevleri dosyası projesi (Windows)
- MFC ActiveXControl
- Yerel birim testi projesi
- Google Test

Evrensel Windows Platformu (C++/CX):
- Boş Uygulama
- DirectX 11 ve XAML uygulaması
- DirectX 11 uygulaması
- DirectX 12 uygulaması 
- Birim testi uygulaması 
- DLL 
- Windows Çalışma Zamanı Bileşeni 
- Statik kitaplık 
- Windows uygulaması paketleme projesi

Linux:
- Konsol uygulaması (Linux)
- Boş proje (Linux)
- Raspberry Pi Blink
- Derleme görevleri dosyası projesi (Linux)

## <a name="tools"></a>Araçlar

- Artımlı bağlayıcı (Link.exe)
- Microsoft derleme görevleri dosyası Yardımcısı (Nmake.exe)
- LIB Generator (Lib.exe)
- Windows Kaynak derleyicisi (Rc.exe)
- Windows kaynaktan nesneye dönüştürücü (CvtRes.exe)
- Bilgi Bakımı yardımcı (BscMake.exe) Gözat
- C++ ad Undecorator (Undname.exe)
- COFF/PE Dumper (Dumpbin.exe)
- COFF/PE Düzenleyicisi (Editbin.exe)
- MASM (Ml.exe)
- Spy++
- ErrLook
- AtlTrace
- Çıkarsama Kuralları
- Profil destekli iyileştirmeler

## <a name="debugging-features"></a>Hata ayıklama özellikleri

- Yerel hata ayıklama
- natvis (yerel tür görselleştirme)
- Grafiksel hata ayıklama
- Yönetilen hata ayıklama
- GPU kullanımı
- Bellek kullanımı
- Uzaktan Hata Ayıklama
- SQL hata ayıklama
- Statik kod analizi

## <a name="designers-and-editors"></a>Tasarımcılar ve düzenleyiciler

- XAML Tasarımcısı
- CSS stil Tasarımcısı/Düzenleyicisi
- HTML Tasarımcısı/Düzenleyicisi
- XML Düzenleyicisi
- Kaynak Kod Düzenleyicisi
- Üretkenlik özellikleri: Yeniden düzenleme, EDG IntelliSense altyapısı C++ kod biçimlendirme
- Windows Form Tasarımcısı
- Veri Tasarımcısı
- Yerel Kaynak Düzenleyicisi (.rc dosyaları)
- Kaynak Düzenleyicileri
- Model düzenleyicisi
- Gölgelendirici tasarımcısı
- Canlı bağımlılık doğrulama (yalnızca Kurumsal)
- Mimari katman diyagramları (yalnızca Kurumsal)
- Mimari doğrulama (yalnızca Kurumsal)
- Kod kopyası (yalnızca Kurumsal)

## <a name="data-features"></a>Veri özellikleri

- Veri Tasarımcısı
- Veri nesneleri
- Web Hizmetleri
- Server Explorer

## <a name="automation-and-extensibility"></a>Otomasyon ve genişletilebilirlik

- Genişletilebilirlik nesne modelleri
- Kod modeli
- Proje Modeli
- Kaynak Düzenleyicisi modeli
- Sihirbaz modeli
- Hata ayıklayıcı nesne modeli

## <a name="application-lifecycle-management-tools"></a>Uygulama yaşam döngüsü Yönetim Araçları

- Birim testi (Microsoft yerel C++, Boost.Test, Google Test, CTest)
- Kod Haritası ve bağımlılık grafikleri (Professional ve Enterprise)
- Kod kapsamı (yalnızca Kurumsal)
- El ile test (yalnızca Kurumsal)
- Keşif testi (yalnızca Kurumsal)
- Test çalışması Yönetimi (yalnızca Kurumsal)
- Kod Haritası hata ayıklayıcı tümleştirmesi (yalnızca Kurumsal)
- Live Unit Testing (yalnızca Kurumsal)
- IntelliTrace (yalnızca Kurumsal)
- Intellitest (yalnızca Kurumsal)
- Microsoft Fakes (birim testi yalıtımı) (yalnızca Kurumsal)
- Kod kapsamı (yalnızca Kurumsal)

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio'yu yükleyin](/visualstudio/install/install-visual-studio)<br/>
[Visual Studio'daki yenilikler](/visualstudio/ide/whats-new-in-visual-studio)<br/>
[C++Visual Studio Proje türleri](../build/reference/visual-cpp-project-types.md)

::: moniker-end

::: moniker range="<=vs-2017"

Aşağıdaki tablolarda görsel Göster C++ Visual Studio 2017'de kullanılabilen özellikleri. Bir hücredeki X, özelliğin kullanılabilir olduğunu gösterir; boş bir hücreye, özelliğin kullanılabilir olmadığını gösterir. Parantez içindeki Notlar bir özelliğin kullanılabileceğini, ancak sınırlı olduğunu gösterir.

## <a name="platforms"></a>Platformlar

||||||
|-|-|-|-|-|
|Platform|Windows 10 için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Visual Studio Community/Professional|Visual Studio Enterprise|
|Windows Masaüstü||X|X|X|
|Evrensel Windows Platformu ((telefon, tablet, PC, Xbox, IOT ve HoloLens))|X||X|X|
|Linux|X|X|
|Microsoft Store 8.1|||X|X|
|Windows Phone 8.0|||X|X|
|Android|||X|X|
|iOS|||X|X|

## <a name="compilers"></a>Derleyicileri

|Derleyici|Windows için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Visual Studio Professional / Community|Visual Studio Enterprise|
|--------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|32-bit X86 MSVC derleyici|X|X|X|X|
|X86_arm çapraz derleyici|X||X|X|
|X64 64 bit MSVC derleyicisi|||X|X|
|X86_ x64 çapraz derleyici|X|X|X|X|

## <a name="libraries-and-headers"></a>Kitaplıklar ve üstbilgiler

|Kitaplık veya başlık|Windows için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Visual Studio Professional / Community|Visual Studio Enterprise|
|-----------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Windows üstbilgiler ve kitaplıkları ve CRT kitaplığı|(X)|X|X|X|
|C++ Standart Kitaplığı|X|X|X|X|
|ATL|||X|X|
|MFC|||X|X|
|.NET Framework sınıf kitaplığı||X|X|X|
|.NET için C++ destek kitaplığı||X|X|X|
|OpenMP 2.0|X|X|X|X|

## <a name="project-templates"></a>Proje şablonları

|Şablon|Windows için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Visual Studio Professional / Community|Visual Studio Enterprise|
|--------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|XAML şablonları için UWP, Windows 8.1, Windows Phone 8.0.|X||X|X|
|Direct3D Uygulaması|X||X|X|
|DLL (Evrensel Windows)|X||X|X|
|Statik kitaplık (Evrensel Windows)|X||X|X|
|Windows Çalışma Zamanı Bileşeni|X||X|X|
|Birim testi uygulaması (Evrensel Windows)|X||X|X|
|ATL projesi|||X|X|
|Sınıf kitaplığı (CLR)||X|X|X|
|CLR konsol uygulaması||X|X|X|
|CLR boş proje||X|X|X|
|Özel Sihirbaz|||X|X|
|Boş Proje||X|X|X|
|Derleme görevleri dosyası projesi||X|X|X|
|MFC ActiveX denetimi|||X|X|
|MFC uygulaması|||X|X|
|MFC DLL|||X|X|
|Test projesi|X|X|X|X|
|Win32 konsol uygulaması||X|X|X|
|Win32 projesi||X|X|X|

## <a name="tools"></a>Araçlar

|Aracı|Windows için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Visual Studio Professional / Community|Visual Studio Enterprise|
|----------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Artımlı bağlayıcı (Link.exe)|X|X|X|X|
|Program bakım Yardımcısı (Nmake.exe)||X|X|X|
|LIB Generator (Lib.exe)|X|X|X|X|
|Windows Kaynak derleyicisi (Rc.exe)|X|X|X|X|
|Windows kaynaktan nesneye dönüştürücü (CvtRes.exe)||X|X|X|
|Bilgi Bakımı yardımcı (BscMake.exe) Gözat|X|X|X|X|
|C++ ad Undecorator (Undname.exe)|X|X|X|X|
|COFF/PE Dumper (Dumpbin.exe)|X|X|X|X|
|COFF/PE Düzenleyicisi (Editbin.exe)|X|X|X|X|
|MASM (Ml.exe)|||X|X|
|Spy++|||X|X|
|ErrLook|||X|X|
|AtlTrace|||X|X|
|Devenv.com|||X|X|
|Çıkarsama Kuralları|||X|X|
|VCBuild .vcproj projelerini MSBuild'e (VCUpgrade.exe) yükseltme|X|X|X|X|
|Profil destekli iyileştirmeler|||X|X|

## <a name="debugging-features"></a>Hata ayıklama özellikleri

|Hata ayıklama özelliği|Windows için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Visual Studio Professional / Community|Visual Studio Enterprise|
|-----------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Yerel hata ayıklama|X|X|X|X|
|natvis (yerel tür görselleştirme)|X|X|X|X|
|Grafiksel hata ayıklama|X||X|X|
|Yönetilen hata ayıklama||X|X|X|
|GPU kullanımı|X||X|X|
|Bellek kullanımı|X||X|X|
|Uzaktan Hata Ayıklama|X|X|X|X|
|SQL hata ayıklama|||X|X|
|Statik kod analizi|Sınırlı|Sınırlı|X|X|

## <a name="designers-and-editors"></a>Tasarımcılar ve düzenleyiciler

|Tasarımcı veya düzenleyici|Windows için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Visual Studio Professional / Community|Visual Studio Enterprise|
|------------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|XAML Tasarımcısı|X||X|X|
|CSS stil Tasarımcısı/Düzenleyicisi|X|X|X|X|
|HTML Tasarımcısı/Düzenleyicisi|X|X|X|X|
|XML Düzenleyicisi|X|X|X|X|
|Kaynak Kod Düzenleyicisi|X|X|X|X|
|Üretkenlik özellikleri: Yeniden düzenleme, IntelliSense, C++ kod biçimlendirme|X|X|X|X|
|Windows Form Tasarımcısı||X|X|X|
|Veri Tasarımcısı|||X|X|
|Yerel Kaynak Düzenleyicisi (.rc dosyaları)|||X|X|
|Kaynak Düzenleyicileri|X|X|X|X|
|Model düzenleyicisi|X||X|X|
|Gölgelendirici tasarımcısı|X||X|X|

## <a name="data-features"></a>Veri özellikleri

|Veri özelliği|Windows için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Visual Studio Professional / Community|Visual Studio Enterprise|
|------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Veri Tasarımcısı|||X|X|
|Veri nesneleri|||X|X|
|Web Hizmetleri|||X|X|
|Server Explorer|||X|X|

## <a name="build-and-project-systems"></a>Derleme ve proje sistemleri

|Yapı veya proje özelliği|Windows için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Visual Studio Professional / Community|Visual Studio Enterprise|
|------------------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Komut satırı yapıları (msbuild.exe)|X|X|X|X|
|Yerel çoklu sürüm desteği||X|X|X|
|Yönetilen çoklu sürüm desteği||X|X|X|
|Paralel yapılar|X|X|X|X|
|Derleme özelleştirmeleri|X|X|X|X|
|Özellik sayfaları genişletilebilirliği|X|X|X|X|

## <a name="automation-and-extensibility"></a>Otomasyon ve genişletilebilirlik

|Otomasyon ve genişletilebilirlik|Windows için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Visual Studio Professional / Community|Visual Studio Enterprise|
|----------------------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Genişletilebilirlik nesne modelleri|||X|X|
|Kod modeli|||X|X|
|Proje Modeli|||X|X|
|Kaynak Düzenleyicisi modeli|||X|X|
|Sihirbaz modeli|||X|X|
|Hata ayıklayıcı nesne modeli|||X|X|

## <a name="application-lifecycle-management-tools"></a>Uygulama yaşam döngüsü Yönetim Araçları

||||||
|-|-|-|-|-|
|Aracı|Windows için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Visual Studio Professional / Community|Visual Studio Enterprise|
|Birim test etme (yerel çerçeve)|X|X|X|X|
|Birim test etme (yönetilen framework)||X|X|X|
|Kod kapsamı||||X|
|El ile test etme||||X|
|Keşif testi||||X|
|Test çalıştırması yönetimi||||X|
|Kod Haritası ve bağımlılık grafikleri|||salt okunur|X|
|Kod Haritası hata ayıklama||||X|

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio'yu yükleyin](/visualstudio/install/install-visual-studio)<br/>
[Visual Studio'daki yenilikler](/visualstudio/ide/whats-new-in-visual-studio)<br/>
[C++Visual Studio Proje türleri](../build/reference/visual-cpp-project-types.md)

::: moniker-end
