---
title: Visual Studio'da C++ projeleri derleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Visual C++ projects, building
- projects [C++], building
- builds [C++], about building in Visual Studio
ms.assetid: 9e8bc1a2-bb17-4951-937a-c757ed88d2d1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0da2464684a06b62c6e22ea04bb68a01dc36f42b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46382356"
---
# <a name="building-c-projects-in-visual-studio"></a>Visual Studio'da C++ Projeleri Derleme

Visual Studio tümleşik geliştirme ortamında (IDE) bütün bir çözüm ya da bunu yalnızca bir proje oluşturmak için birkaç yolu vardır. Ayrıca, derleme ayarlarını değiştirin ve geliştirme sürecini daha verimli hale getirmek için özel yapı adımları belirtin.

Visual Studio'da Aç ve seçili bir çözüm oluşturmak için **Çözüm Gezgini**, şunları yapabilirsiniz:

- Menü çubuğunda, **derleme**, **Çözümü Derle**.

- Veya **Çözüm Gezgini**, çözüm için kısayol menüsünü açın ve ardından **Çözümü Derle**.

- Veya F7'ye basın. (C/C++ geliştirme ayarları için varsayılan klavye kısayol budur.)

- Veya [komut penceresi](/visualstudio/ide/reference/command-window) (menü çubuğunda, **görünümü**, **diğer Windows**, **komut penceresi**), girin `Build.BuildSolution`.

- Veya [hızlı başlatma](/visualstudio/ide/reference/quick-launch-environment-options-dialog-box) kutusuna `build build solution`.

Seçili bir projeyi derlemek için **Çözüm Gezgini**, şunları yapabilirsiniz:

- Menü çubuğunda, **derleme**, **derleme \<proje adı >**.

- Veya **Çözüm Gezgini**, proje için kısayol menüsünü açın ve ardından **yapı**.

- Veya komut penceresinde (menü çubuğunda, **görünümü**, **diğer Windows**, **komut penceresi**), girin `Build.BuildOnlyProject`.

- Veya, Hızlı Başlat kutusuna `build project only build only <project name>`.

Visual Studio'da Visual C++ uygulaması derlerken, birçok yapı ayarları projenin özellik sayfaları iletişim kutusunda değiştirebilirsiniz. Proje özelliklerini ayarlama hakkında daha fazla bilgi için bkz: [Working with Project Properties](../ide/working-with-project-properties.md).

IDE'yi oluşturmak, derlemek ve C++ proje hata ayıklama için nasıl kullanılacağı hakkında bir örnek için bkz. [izlenecek yol: C++ ile Visual Studio IDE'yi keşfedin](/visualstudio/ide/getting-started-with-cpp-in-visual-studio). C + oluşturmak için IDE'yi kullanma hakkında bir örnek +/ CLR proje bkz [izlenecek yol: Visual Studio'da CLR'yi hedefleyen C++ programını derleme](../ide/walkthrough-compiling-a-cpp-program-that-targets-the-clr-in-visual-studio.md). Bir Windows çalışma zamanı uygulaması oluşturmak için IDE'yi kullanma hakkında bir örnek için bkz. [C++ kullanarak ilk Windows çalışma zamanı uygulamasını oluşturma](https://msdn.microsoft.com/library/windows/apps/hh974580.aspx).

Derleme, derleme ayarlarını değiştirebilir ve özel belirleme hakkında daha fazla derleme adımları okumak için aşağıdaki makalelere bakın.

## <a name="in-this-section"></a>Bu Bölümde

[Özel Derleme Adımlarını ve Derleme Olaylarını Anlama](../ide/understanding-custom-build-steps-and-build-events.md)<br>
Tümleşik geliştirme ortamında yapı işleminin nasıl özelleştirileceğini açıklar.

[Genel Derleme Komutları ve Özellikler Makroları](../ide/common-macros-for-build-commands-and-properties.md)<br>
Burada dizeleri kabul kullanabileceğiniz makroları listeler.

[Harici Projeler Derleme](../ide/building-external-projects.md)<br>
Tümleşik geliştirme ortamı dışında olanakları kullanan proje oluşturma açıklanır.

[Proje Dosyaları](../ide/project-files.md)<br>
.Vcxproj dosyası XML yapısını gösterir.

## <a name="related-sections"></a>İlgili Bölümler

[VC ++ dizinleri, projeler, Seçenekler iletişim kutusu](vcpp-directories-property-page.md)<br>
(Yalnızca MSBuild Proje) Yürütülebilir dosyalar için arama yolunu değiştirirseniz, dosyaları, kitaplık dosyalarını ve kaynak kodu dosyaları derleme sırasında dahil anlatılmaktadır.

[Derleme ve Oluşturma](/visualstudio/ide/compiling-and-building-in-visual-studio)<br>
Visual Studio içinden yapı hakkında bilgiler sağlar.

[C/C++ Programları Oluşturma](../build/building-c-cpp-programs.md)<br>
Programınızın komut satırından veya Visual Studio'nun tümleşik geliştirme ortamından oluşturmayı açıklayan konulara bağlantılar sağlar.

[C/C++ Derleme Başvurusu](../build/reference/c-cpp-building-reference.md)<br>
Bağlantılar programlarda, C++, derleyici ve bağlayıcı seçenekleri ve ek derleme araçları oluşturmaya genel bir bakış sağlar.

[Önceki Visual C++ Sürümü Projelerini Yükseltme](../porting/upgrading-projects-from-earlier-versions-of-visual-cpp.md)<br>
C++ projenize derleyici araç setini daha yeni sürümlerine yükseltme konuları kapsayan konulara bağlantılar sağlar.

[Visual C++ taşıma ve yükseltme Kılavuzu](../porting/visual-cpp-porting-and-upgrading-guide.md) Visual Studio'nun önceki sürümlerinde oluşturulan C++ uygulamalarını yükseltme ve ayrıca Visual Studio dışındaki araçlarla oluşturulmuş uygulamaları geçirme hakkında ayrıntılı bilgi.

## <a name="see-also"></a>Ayrıca Bkz.

[Evrensel Windows Uygulamaları (C++)](../windows/universal-windows-apps-cpp.md)