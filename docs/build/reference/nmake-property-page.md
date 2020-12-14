---
description: 'Daha fazla bilgi edinin: NMake Özellik sayfası'
title: NMake Özellik sayfası (Windows C++) | Microsoft Docs
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCNMakeTool.ReBuildCommandLine
- VC.Project.VCNMakeTool.CleanCommandLine
- VC.Project.VCNMakeTool.Output
- VC.Project.VCNMakeTool.BuildCommandLine
helpviewer_keywords:
- NMake property page
ms.assetid: bd20cb52-9f1d-4240-b4fc-4f43205ac94b
ms.openlocfilehash: 58256ad8542e7d411769efb661970f9c41797ec3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196808"
---
# <a name="nmake-property-page"></a>NMake Özellik Sayfaları

**NMAKE** özelliği sayfası NMAKE projeleri için derleme ayarları belirtmenize olanak tanır. (NMAKE, Microsoft 'un [Make](https://wikipedia.org/wiki/Make_(software))uygulamasıdır.)

NMake projeleri hakkında daha fazla bilgi için bkz. [makefile projesi oluşturma](creating-a-makefile-project.md). Windows dışı derleme görevleri dosyası projeleri için bkz. [derleme görevleri dosyası proje özellikleri (Linux c++)](../../linux/prop-pages/makefile-linux.md), [genel proje özellikleri (Android c++ makefile)](/visualstudio/cross-platform/general-makefile-android-prop-page) veya [NMAKE özellikleri (Android c++)](/visualstudio/cross-platform/nmake-android-prop-page).

**NMAKE** özelliği sayfası aşağıdaki özellikleri içerir.

## <a name="uielement-list"></a>UIElement Listesi

- **Derleme komut satırı**

   **Derleme menüsünde** **derleme** tıklandığında çalıştırılacak komutu belirtir.

- **Tüm komut satırını yeniden derle**

   **Tümünü yeniden derle** , **derleme** menüsüne tıklandığı zaman çalıştırılacak komutu belirtir.

- **Temizle komut satırı**

   **Derleme** menüsünde **temiz** tıklandığında çalıştırılacak komutu belirtir.

- **Çıktı**

   Komut satırı için çıktıyı içerecek dosyanın adını belirtir. Varsayılan olarak, bu dosya adı proje adına göre belirlenir.

- **Önişlemci tanımları**

   Kaynak dosyaların kullandığı tüm Önişlemci tanımlarını belirtir. Varsayılan değer, geçerli platform ve yapılandırma tarafından belirlenir.

- **Arama yolunu ekle**

   Derleyicinin içerme dosyalarını arayacağı dizinleri belirtir.

- **Zorunlu ekler**

   Proje dosyalarına dahil edilmese de Önişlemci tarafından otomatik olarak işlenen dosyaları belirtir.

- **Bütünleştirilmiş kod arama yolu**

   .NET Framework, .NET derlemelerini çözümlemek için ne zaman arayacağını arayacağı dizinleri belirtir.

- **Derlemeler kullanılarak zorlandı**

   .NET Framework otomatik olarak işlediği derlemeleri belirtir.

- **Ek seçenekler**

   IntelliSense için C++ dosyalarını ayrıştırırken kullanılacak ek derleyici anahtarlarını belirtir.

**NMAKE** Özellik sayfasına erişme hakkında daha fazla bilgi için bkz. [Visual Studio 'da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

Bu nesnenin üyelerine programlı bir şekilde erişme hakkında daha fazla bilgi için bkz <xref:Microsoft.VisualStudio.VCProjectEngine.VCNMakeTool> ..

## <a name="see-also"></a>Ayrıca bkz.

[C++ proje özellik sayfası başvurusu](property-pages-visual-cpp.md)<br>
