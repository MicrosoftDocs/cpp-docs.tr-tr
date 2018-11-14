---
title: 'Nasıl yapılır: 64 Bit hedeflemek için Visual C++ projeleri x64 yapılandırma platformları'
ms.date: 11/04/2016
helpviewer_keywords:
- platforms [C++], 64-bit
- 64-bit programming [C++], configuring projects
- project configurations [C++]
ms.assetid: 2b9ae001-df36-4750-83b2-982145d632ad
ms.openlocfilehash: c0c734648b084c3f58577cb56984e3ea003a6a8e
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51523943"
---
# <a name="how-to-configure-visual-c-projects-to-target-64-bit-x64-platforms"></a>Nasıl yapılır: 64 Bit hedeflemek için Visual C++ projeleri x64 yapılandırma platformları

Visual Studio IDE'de proje yapılandırmalarını, 64-bit, hedeflemek için C++ uygulamaları x64 platformları ayarlamak için kullanabilirsiniz. Ayrıca, bir 64-bit proje yapılandırması Win32 Proje ayarlarını geçirebilirsiniz.

### <a name="to-set-up-c-applications-to-target-64-bit-platforms"></a>64 bit platformlarını hedeflemek için C++ uygulamalar ayarlamak için

1. Yapılandırmak istediğiniz C++ projesini açın.

1. Proje özellik sayfalarını açın. Daha fazla bilgi için [Working with Project Properties](../ide/working-with-project-properties.md).

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

  - [/Makine](../build/reference/machine-specify-target-platform.md) bağlayıcı seçeneğini ayarlamak **/MACHINE:X 64**.

  - **Çıkışı Kaydet** olan kapalı. Daha fazla bilgi için [bağlayıcı özellik sayfaları](../ide/linker-property-pages.md).

  - **Hedef ortam** ayarlanır **/env x64**. Daha fazla bilgi için [MIDL özellik sayfaları: Genel](../ide/midl-property-pages-general.md).

  - **Parametreleri doğrula** temizlenir ve varsayılan değerine sıfırlayın. Daha fazla bilgi için [MIDL özellik sayfaları: Gelişmiş](../ide/midl-property-pages-advanced.md).

  - Varsa **hata ayıklama bilgi biçimi** ayarlandı **/zi** Win32 Proje yapılandırmasında sonra ayarlanmış **/zi** 64-bit proje yapılandırmasında. Daha fazla bilgi için [/z7, / zi, /zı (hata ayıklama bilgileri biçimi)](../build/reference/z7-zi-zi-debug-information-format.md).

  > [!NOTE]
  > Bu proje özellikleri hiçbiri dosya düzeyine kılınırsa değiştirilir.

## <a name="see-also"></a>Ayrıca Bkz.

[.NET framework 64-bit uygulamalar](/dotnet/framework/64-bit-apps)<br/>
[Visual C++’ı 64 bit, x64 hedefler için yapılandırma](../build/configuring-programs-for-64-bit-visual-cpp.md)<br/>
[64 Bit Uygulamalarda Hata Ayıklama](/visualstudio/debugger/debug-64-bit-applications)