---
title: Visual C++ Araçları ve özellikleri Visual Studio sürümleri
ms.date: 02/28/2018
helpviewer_keywords:
- versions [C++]
- Visual C++, versions
- editions [C++]
ms.assetid: 3d88607b-9cc4-490a-8d4c-31ee7610a26f
ms.openlocfilehash: 7f40e59ae3e5e883827a212a16d1dd19822dc136
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50463758"
---
# <a name="visual-c-tools-and-features-in-visual-studio-editions"></a>Visual C++ Araçları ve özellikleri Visual Studio sürümleri

Aşağıdaki tablolarda, Visual Studio'da bulunan Visual C++ özellikleri gösterilmiştir. Bir hücredeki X, özelliğin kullanılabilir olduğunu gösterir; boş bir hücreye, özelliğin kullanılabilir olmadığını gösterir. Parantez içindeki Notlar bir özelliğin kullanılabileceğini, ancak sınırlı olduğunu gösterir.

## <a name="platforms"></a>Platformlar

||||||
|-|-|-|-|-|
|Platform|Windows 10 için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Visual Studio Community/Professional|Visual Studio Enterprise|
|Windows Masaüstü||X|X|X|
|Evrensel Windows Platformu ((telefon, tablet, PC, Xbox, IOT ve HoloLens))|X||X|X|
|Microsoft Store 8.1|||X|X|
|Windows Phone 8.0|||X|X|
|Android|||X|X|
|iOS|||X|X|

## <a name="compilers"></a>Derleyicileri

|Derleyici|Windows için Visual Studio Express|Windows Masaüstü için Visual Studio Express|Visual Studio Professional / Community|Visual Studio Enterprise|
|--------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|
|32-bit X86 derleyici|X|X|X|X|
|X86_arm çapraz derleyici|X||X|X|
|64-bit x64 derleyici|||X|X|
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
|OpenMP|X|X|X|X|

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

## <a name="see-also"></a>Ayrıca Bkz.

[Visual Studio'yu yükleyin](/visualstudio/install/install-visual-studio)<br/>
[Visual Studio'daki yenilikler](/visualstudio/ide/whats-new-in-visual-studio)<br/>
[Visual C++ Proje Türleri](../ide/visual-cpp-project-types.md)<br/>
[SQL Server Veri Araçları](https://msdn.microsoft.com/library/hh272686)<br/>
