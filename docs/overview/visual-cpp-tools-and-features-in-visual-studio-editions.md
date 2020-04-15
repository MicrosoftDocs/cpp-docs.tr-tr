---
title: Visual Studio Sürümlerinde C++ Araçları ve Özellikleri
ms.date: 05/21/2019
helpviewer_keywords:
- tools and platforms [C++]
ms.assetid: 3d88607b-9cc4-490a-8d4c-31ee7610a26f
ms.openlocfilehash: 88eb66440df023254cb806c03a00aa2d71980305
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366790"
---
# <a name="c-tools-and-features-in-visual-studio-editions"></a>Visual Studio Sürümlerinde C++ Araçları ve Özellikleri

::: moniker range=">=vs-2019"

Aşağıdaki C++ özellikleri Visual Studio 2019'da mevcuttur. Aksi belirtilmedikçe, tüm özellikler tüm sürümlerde mevcuttur: Visual Studio Community, Visual Studio Professional ve Visual Studio Enterprise. Bazı özellikler, Visual Studio Yükleyiciile yükleyebileceğiniz belirli iş yükleri veya isteğe bağlı bileşenler gerektirir.

## <a name="platforms"></a>Platformlar

- Windows Masaüstü
- Evrensel Windows Platformu ((tablet, PC, Xbox, IoT ve HoloLens))
- Linux
- Android
- iOS

## <a name="compilers"></a>Derleyiciler

- X86, x64, ARM ve ARM64 için MSVC 32 bit derleyici
- X86, x64, ARM ve ARM64 için MSVC 64 bit derleyici
- ARM için GCC çapraz derleyicisi
- Clang/LLVM
  - Windows'da, Clang/LLVM 7.0, x86 veya x64 (yalnızca CMake desteği) hedefleme. Diğer Clang sürümleri işe yarayabilir, ancak resmi olarak desteklenmez.
  - Linux'ta, dağıtım tarafından desteklenen herhangi bir Clang/LLVM kurulumu.

## <a name="c-workloads"></a>C++ İş Yükleri

Visual Studio, C++ geliştirme için aşağıdaki iş yüklerini içerir. .NET Masaüstü Geliştirme, Python Geliştirme, Azure Geliştirme, Visual Studio Uzantısı Geliştirme ve diğerleri gibi diğer iş yükleriyle birlikte bunların herhangi birini veya tümünü yükleyebilirsiniz.

### <a name="desktop-development-with-c"></a>C++ ile masaüstü geliştirme

Dahil:

- C++ çekirdek masaüstü özellikleri

İsteğe Bağlı Bileşenler:

- MSVC v142 - VS 2019 C++ x64/x86 yapı araçları (v14.21)
- Windows 10 SDK (10.0.17763.0)
- Tam Zamanında hata ayıklama
- C++ profil oluşturma araçları
- C++ CWindows için araçlar yapın
- V142 yapı araçları için C++ ATL (x86 & x64)
- Boost.Test için Test Adaptörü
- Google Test için Test Adaptörü
- Live Share
- IntelliCode
- IntelliTrace (Yalnızca Kurumsal)
- V142 yapı araçları için C++ MFC (x86 & x64)
- V142 yapı araçları için C++/CLI desteği (14,21)
- V142 yapı araçları için C++ Modülleri (x64/x86 – deneysel)
- Windows için Clang derleyicisi
- IncrediBuild - Yapı İvme
- Windows 10 SDK (10.0.17134.0)
- Windows 10 SDK (10.0.16299.0)
- MSVC v141 - VS 2017 C++ x64/x86 yapı araçları (v14.16)
- MSVC v140 - VS 2015 C++ yapı araçları (v14.00)

### <a name="linux-development-with-c"></a>C++ ile Linux geliştirme

Dahil:

- C++ temel özellikleri
- Windows Universal C Çalışma Zamanı
- Linux Geliştirme için C++

İsteğe Bağlı Bileşenler:

- Linux için C++ CMake araçları
- Gömülü ve IoT geliştirme araçları

### <a name="universal-windows-platform-development"></a>Evrensel Windows Platformu geliştirme

Dahil:

- Visual Studio için Blend
- .NET Yerli ve .NET Standardı
- NuGet paket yöneticisi
- Evrensel Windows Platformu araçları
- Windows 10 SDK (10.0.17763.0)

İsteğe Bağlı Bileşenler:

- IntelliCode
- IntelliTrace (Yalnızca Kurumsal)
- USB Aygıt Bağlantısı
- C++ (v142) Evrensel Windows Platformu araçları
- C++ (v141) Evrensel Windows Platformu araçları
- DirectX için grafik hata ayıklayıcı ve GPU profil oluşturucu
- Windows 10 SDK (10.0.18362.0)
- Windows 10 SDK (10.0.17134.0)
- Windows 10 SDK (10.0.16299.0)
- Mimarlık ve analiz araçları

### <a name="c-game-development"></a>C++ Oyun Geliştirme

Dahil:

- C++ temel özellikleri
- Windows Universal C Çalışma Zamanı
- C++ 2019 Yeniden Dağıtılabilir Güncelleştirme
- MSVC v142 - VS 2019 C++ x64/x86 yapı araçları (v14.21)

İsteğe Bağlı Bileşenler:

- C++ profil oluşturma araçları
- Windows 10 SDK (10.0.17763.0)
- IntelliCode
- IntelliTrace (Yalnızca Kurumsal)
- Windows 10 SDK (10.0.17134.0)
- Windows 10 SDK (10.0.16299.0)
- IncrediBuild - Yapı İvme
- Cocos
- Unreal Motor yükleyici
- Unreal motoru için Android IDE desteği

### <a name="mobile-development-with-c"></a>C++ ile mobil geliştirme

Dahil:

- C++ temel özellikleri
- Android SDK kurulumu (API level 25) (C++ile Mobil geliştirme için yerel yükleme)

İsteğe Bağlı Bileşenler:

- Android NDK (R16B)
- Apaçi Karınca (1.9.3)
- C++ Android geliştirme araçları
- IntelliCode
- Google Android Emülatörü (API Level 25) (yerel yükleme)
- Intel Donanım Hızlandırılmış Yürütme Yöneticisi (HAXM) (yerel yükleme)
- Android NDK (R16B) (32bit)
- C++ iOS geliştirme araçları
- IncrediBuild - Yapı İvme

## <a name="individual-components"></a>Tek tek bileşenler

Bu bileşenleri herhangi bir iş yükünden bağımsız olarak yükleyebilirsiniz.

- JavaScript tanılama
- Live Share
- V142 yapı araçları için C++ Evrensel Windows Platformu çalışma süresi
- ClickOnce Yayıncılık
- Microsoft Visual Studio Yükleyici Projeleri

## <a name="libraries-and-headers"></a>Kütüphaneler ve Üstbilgi

- Windows üstbilgi ve kitaplıklar
- Windows Evrensel C Çalışma Süresi (CRT)
- C++ Standart Kitaplığı
- ATL
- MFC
- .NET Framework sınıf kitaplığı
- C++ Destek Kitaplığı için .NET
- OpenMP 2.0
- vcpkg kataloğu ile 900'den fazla açık kaynak kitaplık

## <a name="build-and-project-systems"></a>Yapı ve Proje Sistemleri

- CMake
- Open Folder üzerinden herhangi bir yapı sistemi
- Komut satırı oluşturur (msbuild.exe)
- Yerel Çoklu hedefleme
- Yönetilen Çoklu hedefleme
- Paralel Yapılar
- Özelleştirmeler Oluşturun
- Özellik Sayfaları Genişletilebilirlik

## <a name="project-templates"></a>Proje Şablonları

Aşağıdaki proje şablonları, yüklediğiniz iş yüklerine bağlı olarak kullanılabilir.

Windows Masaüstü:

- Boş Proje
- Konsol Uygulaması
- Windows Masaüstü Sihirbazı
- Windows Masaüstü Uygulaması
- Paylaşılan Öğeler Projesi
- MFC Uygulaması
- Dinamik Bağlantı Kitaplığı
- CLR Boş Proje
- CLR Konsol Uygulaması
- Statik Kitaplık
- CMake Projesi
- ATL Projesi
- MFC Dinamik Bağlantı Kitaplığı
- CLR Sınıf Kütüphanesi
- Makefile Projesi (Windows)
- MFC ActiveXControl
- Yerli Birim Test Projesi
- Google Testi

Evrensel Windows Platformu (C++/CX):

- Boş Uygulama
- DirectX 11 ve XAML Uygulaması
- DirectX 11 Uygulaması
- DirectX 12 Uygulaması
- Ünite Test Uygulaması
- DLL
- Windows Çalışma Zamanı Bileşeni
- Statik Kitaplık
- Windows Uygulaması Paketleme Projesi

Linux:

- Konsol Uygulaması (Linux)
- Boş Proje (Linux)
- Ahududu Pi Blink
- Makefile Projesi (Linux)

## <a name="tools"></a>Araçlar

- Artımlı Bağlayıcı (Link.exe)
- Microsoft Makefile Utility (Nmake.exe)
- Lib Jeneratör (Lib.exe)
- Windows Kaynak Derleyicisi (Rc.exe)
- Windows Kaynak Nesne Dönüştürücü (CvtRes.exe)
- Gözat Bilgi Bakım Programı (BscMake.exe)
- C++ İsim Dekoratör (Undname.exe)
- COFF/PE Damperli (Dumpbin.exe)
- COFF/PE Editörü (Editbin.exe)
- MASM (Ml.exe)
- Spy++
- ErrLook
- AtlTrace
- Çıkarsama Kuralları
- Profil Güdümlü Optimizasyonlar

## <a name="debugging-features"></a>Hata Ayıklama Özellikleri

- Yerel Hata Ayıklama
- natvis (yerli tip görselleştirme)
- Grafik Hata Ayıklama
- Yönetilen Hata Ayıklama
- GPU kullanımı
- Bellek kullanımı
- Uzaktan Hata Ayıklama
- SQL Hata Ayıklama
- Statik Kod Analizi

## <a name="designers-and-editors"></a>Tasarımcılar ve Editörler

- XAML Tasarımcısı
- CSS Stil Tasarımcısı / Editör
- HTML Tasarımcısı/Editörü
- XML Düzenleyicisi
-  Kaynak Kod Düzenleyici
- Verimlilik Özellikleri: Refactoring, EDG IntelliSense motoru, C++ Kod Biçimlendirme
- Windows Form Tasarımcısı
- Veri Tasarımcısı
- Yerel Kaynak Düzenleyicisi (.rc dosyaları)
- Kaynak Düzenleyicileri
- Model düzenleyicisi
- Gölgelendirici tasarımcısı
- Canlı Bağımlılık Doğrulama (Yalnızca Kurumsal)
- Mimari Katman Diyagramları (Yalnızca Kurumsal)
- Mimari Doğrulama (Yalnızca Kurumsal)
- Kod Klon (Yalnızca Kurumsal)

## <a name="data-features"></a>Veri Özellikleri

- Veri Tasarımcısı
- Veri Nesneleri
- Web Hizmetleri
- Sunucu Gezgini

## <a name="automation-and-extensibility"></a>Otomasyon ve Genişletilebilirlik

- Genişletilebilirlik Nesne Modelleri
- Kod Modeli
- Proje Modeli
- Kaynak Düzenleyici Modeli
- Sihirbaz Modeli
- Hata Ayıklama Nesne Modeli

## <a name="application-lifecycle-management-tools"></a>Uygulama Yaşam Döngüsü Yönetim Araçları

- Birim Testi (Microsoft Native C++, Boost.Test, Google Test, CTest)
- Kod eşlemi ve bağımlılık grafikleri (Profesyonel ve Kurumsal)
- Kod kapsamı (Yalnızca Kurumsal)
- Manuel test (Yalnızca Kurumsal)
- Araştırmacı test (Yalnızca Kurumsal)
- Test case yönetimi (Yalnızca Kurumsal)
- Kod eşlemi hata ayıklama tümleştirmesi (Yalnızca Kurumsal)
- Canlı Birim Testi (Yalnızca Kurumsal)
- IntelliTrace (Yalnızca Kurumsal)
- IntelliTest (Yalnızca Kurumsal)
- Microsoft Fakes (Unit Test Yalıtımı) (Yalnızca Kurumsal)
- Kod Kapsamı (Yalnızca Kurumsal)

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio'yu yükleme](/visualstudio/install/install-visual-studio)<br/>
[Visual Studio'da Yenilikler](/visualstudio/ide/whats-new-in-visual-studio)<br/>
[Visual Studio'da C++ proje türleri](../build/reference/visual-cpp-project-types.md)

::: moniker-end

::: moniker range="<=vs-2017"

Aşağıdaki tablolar Visual Studio 2017'de kullanılabilen Visual C++ özelliklerini göstermektedir. Hücredeki X özelliğinin kullanılabilir olduğunu gösterir; boş bir hücre özelliğinin kullanılmadığını gösterir. Parantez içinde notlar bir özelliğin kullanılabilir olduğunu, ancak kısıtlandığını gösterir.

## <a name="platforms"></a>Platformlar

||||||
|-|-|-|-|-|
|Platform|Windows 10 için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Görsel Stüdyo Topluluğu/Profesyonel|Visual Studio Enterprise|
|Windows Masaüstü||X|X|X|
|Evrensel Windows Platformu ((telefon, tablet, PC, Xbox, IoT ve HoloLens))|X||X|X|
|Linux|X|X|
|Microsoft Mağazası 8.1|||X|X|
|Windows Phone 8.0|||X|X|
|Android|||X|X|
|iOS|||X|X|

## <a name="compilers"></a>Derleyiciler

|Derleyici|Windows için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Visual Studio Professional / Topluluk|Visual Studio Enterprise|
|--------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|MSVC 32-bit X86 derleyicisi|X|X|X|X|
|X86_arm çapraz derleyici|X||X|X|
|MSVC 64-bit x64 derleyici|||X|X|
|X86_ x64 çapraz derleyici|X|X|X|X|

## <a name="libraries-and-headers"></a>Kütüphaneler ve Üstbilgi

|Kitaplık veya Üstbilgi|Windows için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Visual Studio Professional / Topluluk|Visual Studio Enterprise|
|-----------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Windows üstbilgi ve kitaplıklar ve CRT kitaplığı|(X)|X|X|X|
|C++ Standart Kitaplığı|X|X|X|X|
|ATL|||X|X|
|MFC|||X|X|
|.NET Framework sınıf kitaplığı||X|X|X|
|C++ Destek Kitaplığı için .NET||X|X|X|
|OpenMP 2.0|X|X|X|X|

## <a name="project-templates"></a>Proje Şablonları

|Şablon|Windows için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Visual Studio Professional / Topluluk|Visual Studio Enterprise|
|--------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|UWP, Windows 8.1, Windows Phone 8.0 için XAML Şablonları|X||X|X|
|Direct3D Uygulaması|X||X|X|
|DLL (Evrensel Pencereler)|X||X|X|
|Statik Kitaplık (Evrensel Windows)|X||X|X|
|Windows Çalışma Zamanı Bileşeni|X||X|X|
|Ünite Test Uygulaması (Evrensel Windows)|X||X|X|
|ATL Projesi|||X|X|
|Sınıf Kitaplığı (CLR)||X|X|X|
|CLR Konsol Uygulaması||X|X|X|
|CLR Boş Proje||X|X|X|
|Özel Sihirbaz|||X|X|
|Boş Proje||X|X|X|
|Makefile Projesi||X|X|X|
|MFC ActiveX Kontrolü|||X|X|
|MFC Uygulaması|||X|X|
|MFC DLL|||X|X|
|Test Projesi|X|X|X|X|
|Win32 Konsol Uygulaması||X|X|X|
|Win32 Projesi||X|X|X|

## <a name="tools"></a>Araçlar

|Araç|Windows için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Visual Studio Professional / Topluluk|Visual Studio Enterprise|
|----------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Artımlı Bağlayıcı (Link.exe)|X|X|X|X|
|Program Bakım Programı (Nmake.exe)||X|X|X|
|Lib Jeneratör (Lib.exe)|X|X|X|X|
|Windows Kaynak Derleyicisi (Rc.exe)|X|X|X|X|
|Windows Kaynak Nesne Dönüştürücü (CvtRes.exe)||X|X|X|
|Gözat Bilgi Bakım Programı (BscMake.exe)|X|X|X|X|
|C++ İsim Dekoratör (Undname.exe)|X|X|X|X|
|COFF/PE Damperli (Dumpbin.exe)|X|X|X|X|
|COFF/PE Editörü (Editbin.exe)|X|X|X|X|
|MASM (Ml.exe)|||X|X|
|Spy++|||X|X|
|ErrLook|||X|X|
|AtlTrace|||X|X|
|Devenv.com|||X|X|
|Çıkarsama Kuralları|||X|X|
|VCBuild .vcproj projelerini MSBuild'e yükseltin (VCUpgrade.exe)|X|X|X|X|
|Profil Güdümlü Optimizasyonlar|||X|X|

## <a name="debugging-features"></a>Hata Ayıklama Özellikleri

|Hata Ayıklama Özelliği|Windows için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Visual Studio Professional / Topluluk|Visual Studio Enterprise|
|-----------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Yerel Hata Ayıklama|X|X|X|X|
|natvis (yerli tip görselleştirme)|X|X|X|X|
|Grafik Hata Ayıklama|X||X|X|
|Yönetilen Hata Ayıklama||X|X|X|
|GPU kullanımı|X||X|X|
|Bellek kullanımı|X||X|X|
|Uzaktan Hata Ayıklama|X|X|X|X|
|SQL Hata Ayıklama|||X|X|
|Statik Kod Analizi|Sınırlı|Sınırlı|X|X|

## <a name="designers-and-editors"></a>Tasarımcılar ve Editörler

|Tasarımcı veya Editör|Windows için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Visual Studio Professional / Topluluk|Visual Studio Enterprise|
|------------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|XAML Tasarımcısı|X||X|X|
|CSS Stil Tasarımcısı / Editör|X|X|X|X|
|HTML Tasarımcısı/Editörü|X|X|X|X|
|XML Düzenleyicisi|X|X|X|X|
| Kaynak Kod Düzenleyici|X|X|X|X|
|Verimlilik Özellikleri: Refactoring, IntelliSense, C++ Kod Biçimlendirme|X|X|X|X|
|Windows Form Tasarımcısı||X|X|X|
|Veri Tasarımcısı|||X|X|
|Yerel Kaynak Düzenleyicisi (.rc dosyaları)|||X|X|
|Kaynak Düzenleyicileri|X|X|X|X|
|Model düzenleyicisi|X||X|X|
|Gölgelendirici tasarımcısı|X||X|X|

## <a name="data-features"></a>Veri Özellikleri

|Veri Özelliği|Windows için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Visual Studio Professional / Topluluk|Visual Studio Enterprise|
|------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Veri Tasarımcısı|||X|X|
|Veri Nesneleri|||X|X|
|Web Hizmetleri|||X|X|
|Sunucu Gezgini|||X|X|

## <a name="build-and-project-systems"></a>Yapı ve Proje Sistemleri

|Yapı veya Proje Özelliği|Windows için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Visual Studio Professional / Topluluk|Visual Studio Enterprise|
|------------------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Komut satırı oluşturur (msbuild.exe)|X|X|X|X|
|Yerel Çoklu hedefleme||X|X|X|
|Yönetilen Çoklu hedefleme||X|X|X|
|Paralel Yapılar|X|X|X|X|
|Özelleştirmeler Oluşturun|X|X|X|X|
|Özellik Sayfaları Genişletilebilirlik|X|X|X|X|

## <a name="automation-and-extensibility"></a>Otomasyon ve Genişletilebilirlik

|Otomasyon ve Genişletilebilirlik|Windows için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Visual Studio Professional / Topluluk|Visual Studio Enterprise|
|----------------------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|Genişletilebilirlik Nesne Modelleri|||X|X|
|Kod Modeli|||X|X|
|Proje Modeli|||X|X|
|Kaynak Düzenleyici Modeli|||X|X|
|Sihirbaz Modeli|||X|X|
|Hata Ayıklama Nesne Modeli|||X|X|

## <a name="application-lifecycle-management-tools"></a>Uygulama Yaşam Döngüsü Yönetim Araçları

||||||
|-|-|-|-|-|
|Araç|Windows için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Visual Studio Professional / Topluluk|Visual Studio Enterprise|
|Ünite Testi (yerel çerçeve)|X|X|X|X|
|Birim Testi (yönetilen çerçeve)||X|X|X|
|Kod kapsamı||||X|
|Manuel test||||X|
|Keşif testi||||X|
|Test çalıştırması yönetimi||||X|
|Kod eşlemi ve bağımlılık grafikleri|||salt okunur|X|
|Kod eşlemi hata ayıklama||||X|

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio'yu yükleme](/visualstudio/install/install-visual-studio)<br/>
[Visual Studio'da Yenilikler](/visualstudio/ide/whats-new-in-visual-studio)<br/>
[Visual Studio'da C++ proje türleri](../build/reference/visual-cpp-project-types.md)

::: moniker-end
