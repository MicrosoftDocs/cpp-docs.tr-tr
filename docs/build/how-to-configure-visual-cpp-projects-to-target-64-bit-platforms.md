---
title: "Nasıl yapılır: Visual Studio'yu yapılandırma C++ platformları hedef 64-Bit için x64 projeleri"
ms.date: 11/04/2016
helpviewer_keywords:
- platforms [C++], 64-bit
- 64-bit programming [C++], configuring projects
- project configurations [C++]
ms.assetid: 2b9ae001-df36-4750-83b2-982145d632ad
ms.openlocfilehash: a063c2f333a755ab86a4f91c9d14d0c65a6d1414
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65446402"
---
# <a name="how-to-configure-visual-studio-c-projects-to-target-64-bit-x64-platforms"></a>Nasıl yapılır: Visual Studio'yu yapılandırma C++ platformları hedef 64-Bit için x64 projeleri

Visual Studio IDE'de proje yapılandırmalarını, 64-bit, hedeflemek için C++ uygulamaları x64 platformları ayarlamak için kullanabilirsiniz. Ayrıca, bir 64-bit proje yapılandırması Win32 Proje ayarlarını geçirebilirsiniz.

### <a name="to-set-up-c-applications-to-target-64-bit-platforms"></a>64 bit platformlarını hedeflemek için C++ uygulamalar ayarlamak için

1. Yapılandırmak istediğiniz C++ projesini açın.

1. Proje özellik sayfalarını açın. Daha fazla bilgi için [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](working-with-project-properties.md).

   > [!NOTE]
   > .NET projeleri için emin **yapılandırma özellikleri** düğüm veya alt düğümlerinden biri seçildiğinde,  **\<Projectname > özellik sayfaları** iletişim kutusu; Aksi takdirde  **Configuration Manager** düğmesi kullanılabilir kalır.

1. Seçin **Configuration Manager** açmak için düğmeyi **Configuration Manager** iletişim kutusu.

1. İçinde **etkin çözüm platformu** aşağı açılan listesinden  **\<yeni … >** açmak için seçeneği **yeni çözüm platformu** iletişim kutusu.

1. İçinde **yazın veya seçin yeni platformu** açılır listede, select 64 bit hedef platformu.

   > [!NOTE]
   > İçinde **yeni çözüm platformu** kullanabileceğiniz iletişim kutusu, **kopyalama ayarlarından** mevcut proje ayarları yeni bir 64-bit proje yapılandırması kopyalamak için seçenek.

1. Seçin **Tamam** düğmesi. Önceki adımda seçtiğiniz platform altında görünür **etkin çözüm platformu** içinde **Configuration Manager** iletişim kutusu.

1. Seçin **Kapat** düğmesine **Configuration Manager** iletişim kutusuna ve ardından **Tamam** düğmesine  **\<Projectname > Özellik sayfaları** iletişim kutusu.

### <a name="to-copy-win32-project-settings-into-a-64-bit-project-configuration"></a>Win32 Proje ayarları bir 64-bit proje yapılandırması kopyalamak için

- Zaman **yeni çözüm platformu** iletişim kutusu, hedef bir 64-bit platformu için bir proje içinde ayarlayabilirsiniz ancak açıksa **Ayarları Şuradan Kopyala** aşağı açılan listesinden **Win32**. Bu proje ayarlarını proje düzeyinde otomatik olarak güncelleştirilir:

  - [/Makine](reference/machine-specify-target-platform.md) bağlayıcı seçeneğini ayarlamak **/MACHINE:X 64**.

  - **Çıkışı Kaydet** olan kapalı. Daha fazla bilgi için [bağlayıcı özellik sayfaları](reference/linker-property-pages.md).

  - **Hedef ortam** ayarlanır **/env x64**. Daha fazla bilgi için [MIDL özellik sayfaları: Genel](reference/midl-property-pages-general.md).

  - **Parametreleri doğrula** temizlenir ve varsayılan değerine sıfırlayın. Daha fazla bilgi için [MIDL özellik sayfaları: Gelişmiş](reference/midl-property-pages-advanced.md).

  - Varsa **hata ayıklama bilgi biçimi** ayarlandı **/zi** Win32 Proje yapılandırmasında sonra ayarlanmış **/zi** 64-bit proje yapılandırmasında. Daha fazla bilgi için [/z7, / zi, /zı (hata ayıklama bilgileri biçimi)](reference/z7-zi-zi-debug-information-format.md).

  > [!NOTE]
  > Bu proje özellikleri hiçbiri dosya düzeyine kılınırsa değiştirilir.

## <a name="see-also"></a>Ayrıca bkz.

[C++ projeleri için 64 bit x64 yapılandırma hedefleri](configuring-programs-for-64-bit-visual-cpp.md)<br/>
[64 Bit Uygulamalarda Hata Ayıklama](/visualstudio/debugger/debug-64-bit-applications)
