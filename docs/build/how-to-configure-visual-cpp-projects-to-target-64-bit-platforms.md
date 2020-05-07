---
title: 'Nasıl yapılır: Visual Studio C++ projelerini 64 bit, x64 platformları hedefleyecek şekilde yapılandırma'
ms.date: 11/04/2016
helpviewer_keywords:
- platforms [C++], 64-bit
- 64-bit programming [C++], configuring projects
- project configurations [C++]
ms.assetid: 2b9ae001-df36-4750-83b2-982145d632ad
ms.openlocfilehash: 762fd5d6ddbb55713cf2fc5e34cb33fb91b08eb9
ms.sourcegitcommit: ce3393846c86e7905ff0c86e4cd6610476809585
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/25/2019
ms.locfileid: "68492236"
---
# <a name="how-to-configure-visual-studio-c-projects-to-target-64-bit-x64-platforms"></a>Nasıl yapılır: Visual Studio C++ projelerini 64 bit, x64 platformları hedefleyecek şekilde yapılandırma

Visual Studio IDE 'deki proje yapılandırmalarının, C++ uygulamalarını 64 bit, x64 platformları hedefleyecek şekilde ayarlamak için kullanabilirsiniz. Ayrıca, Win32 Proje ayarlarını 64 bitlik bir proje yapılandırmasına geçirebilirsiniz.

### <a name="to-set-up-c-applications-to-target-64-bit-platforms"></a>C++ uygulamalarını 64 bitlik platformları hedefleyecek şekilde ayarlamak için

1. Yapılandırmak istediğiniz C++ projesini açın.

1. Bu projenin özellik sayfalarını açın. Daha fazla bilgi için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](working-with-project-properties.md).

   > [!NOTE]
   > .NET projeleri için, **yapılandırma özellikleri** düğümünün veya alt düğümlerinden birinin, ** \<ProjectName> Özellik sayfaları** iletişim kutusunda seçildiğinden emin olun; Aksi takdirde **Configuration Manager** düğmesi kullanılamaz durumda kalır.

1. **Configuration Manager** iletişim kutusunu açmak için **Configuration Manager** düğmesini seçin.

1. **Etkin çözüm platformu** açılan listesinde yeni ** \<... >** seçeneğini seçerek **yeni çözüm platformu** iletişim kutusunu açın.

1. **Yeni platform açılır listesini yazın veya seçin** , 64 bit hedef platformu seçin.

   > [!NOTE]
   > **Yeni çözüm platformu** iletişim kutusunda, mevcut proje ayarlarını yeni 64-bit proje yapılandırmasına kopyalamak Için **Ayarları Kopyala** seçeneğini kullanabilirsiniz.

1. **Tamam** düğmesini seçin. Önceki adımda seçtiğiniz platform, **Configuration Manager** Iletişim kutusunda **etkin çözüm platformu** altında görüntülenir.

1. **Configuration Manager** iletişim kutusunda **Kapat** düğmesini seçin ve sonra ** \<ProjectName> Özellik sayfaları** iletişim kutusunda **Tamam** düğmesini seçin.

### <a name="to-copy-win32-project-settings-into-a-64-bit-project-configuration"></a>Win32 Proje ayarlarını 64 bitlik bir proje yapılandırmasına kopyalamak için

- **Yeni çözüm platformu** iletişim kutusu açık olduğunda, bir projeyi bir 64-bit platformunu hedeflemek üzere ayarlarken, ayarları açılan listeden **Kopyala** listesinden **Win32**öğesini seçin. Bu proje ayarları proje düzeyinde otomatik olarak güncelleştirilir:

  - [/Machine](reference/machine-specify-target-platform.md) bağlayıcı seçeneği **/Machine: x64**olarak ayarlanır.

  - **Çıktıyı kaydet** kapatılmış. Daha fazla bilgi için bkz. [bağlayıcı özellik sayfaları](reference/linker-property-pages.md).

  - **Hedef ortam** , **/env x64**olarak ayarlanmıştır. Daha fazla bilgi için bkz. [MIDL özellik sayfaları](reference/midl-property-pages.md).

  - **Validate parametreleri** temizlenir ve varsayılan değere sıfırlanır. Daha fazla bilgi için bkz. [MIDL özellik sayfaları](reference/midl-property-pages.md).

  - **Hata ayıklama bilgi biçimi** Win32 proje yapılandırmasında **/Zi** olarak ayarlandıysa, 64 bit proje yapılandırmasında **/Zi** olarak ayarlanır. Daha fazla bilgi için bkz. [/Z7,/Zi,/ZI (hata ayıklama bilgileri biçimi)](reference/z7-zi-zi-debug-information-format.md).

  > [!NOTE]
  > Bu proje özelliklerinden hiçbiri dosya düzeyinde geçersiz kılınırsa değiştirilmez.

## <a name="see-also"></a>Ayrıca bkz.

[64 bit, x64 hedefleri için C++ projelerini yapılandırma](configuring-programs-for-64-bit-visual-cpp.md)<br/>
[Hata ayıklama 64-bit uygulamalar](/visualstudio/debugger/debug-64-bit-applications)
