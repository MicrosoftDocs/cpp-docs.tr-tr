---
title: NMake özellik sayfası (C++ Windows) | Microsoft Docs
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCNMakeTool.ReBuildCommandLine
- VC.Project.VCNMakeTool.CleanCommandLine
- VC.Project.VCNMakeTool.Output
- VC.Project.VCNMakeTool.BuildCommandLine
helpviewer_keywords:
- NMake property page
ms.assetid: bd20cb52-9f1d-4240-b4fc-4f43205ac94b
ms.openlocfilehash: c0dbe537635fe6698f814f3d8456f0caa9c8c796
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62320610"
---
# <a name="nmake-property-page"></a>NMake Özellik Sayfaları

**NMake** özellik sayfası NMake projeleri için derleme ayarları belirtmenize olanak sağlar. (NMAKE olan Microsoft uyarlamasını [olun](https://wikipedia.org/wiki/Make_(software)).)

NMake projeleri hakkında daha fazla bilgi için bkz. [bir derleme görevleri dosyası projesi oluşturma](creating-a-makefile-project.md). Windows MakeFile projeleri için bkz: [derleme görevleri dosyası proje özellikleri (Linux C++)](../../linux/prop-pages/makefile-linux.md), [genel proje özellikleri (Android C++ derleme görevleri dosyası)](/visualstudio/cross-platform/general-makefile-android-prop-page) veya [NMake özellikleri (Android C++)](/visualstudio/cross-platform/nmake-android-prop-page).

**NMake** özellik sayfası, aşağıdaki özellikleri içerir.

## <a name="uielement-list"></a>UIElement Listesi

- **Komut satırı derleme**

   Ne zaman çalıştırılacak komutu belirtir **derleme** üzerinde tıklandığında **derleme** menüsü.

- **Rebuild all komut satırı**

   Ne zaman çalıştırılacak komutu belirtir **Rebuild All** üzerinde tıklandığında **derleme** menüsü.

- **Temizle komut satırı**

   Ne zaman çalıştırılacak komutu belirtir **temiz** üzerinde tıklandığında **derleme** menüsü.

- **Output**

   Çıkış komut satırı içerecek dosyanın adını belirtir. Varsayılan olarak, bu dosya adı proje adı temel alır.

- **Önişlemci tanımları**

   Kaynak kullanan dosyaları tüm önişlemci tanımlarını belirtir. Varsayılan değer, geçerli platform ve yapılandırma tarafından belirlenir.

- **Arama Yolu Ekle**

   Derleyici için dahil etme dosyaları nerede arar dizinleri belirtir.

- **Zorlanmış içerir**

   Proje dosyalarında bulunmayan olsa bile, önişlemci otomatik olarak işleyen dosyalarını belirtir.

- **Bütünleştirilmiş kod arama yolu**

   Burada .NET Framework araması ne zaman dizinleri belirtir, .NET derlemelerini çözümlenecek trys.

- **Zorlanarak kullanılan bütünleştirilmiş kodlar**

   .NET Framework otomatik olarak işler bütünleştirilmiş kodları belirtir.

- **Ek Seçenekler**

   C++ dosyaları ayıklarken kullanılacak IntelliSense için herhangi bir ek derleyici anahtarlarını belirtir.

Nasıl erişileceği hakkında daha fazla bilgi için **NMake** özellik sayfasında bakın [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

Bu nesne program aracılığıyla üyelerine erişim hakkında daha fazla bilgi için bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCNMakeTool>.

## <a name="see-also"></a>Ayrıca bkz.

[C++ projesi özellik Sayfa başvurusu](property-pages-visual-cpp.md)<br>
