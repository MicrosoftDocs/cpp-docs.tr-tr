---
description: 'Daha fazla bilgi edinin: özel derleme araçlarını belirtme'
title: Özel Derleme Araçlarını Belirtme
ms.date: 06/05/2018
f1_keywords:
- VC.Project.VCCustomBuildTool.CustomBuildToolBeforeTargets
- VC.Project.VCCustomBuildTool.Outputs
- VC.Project.VCCustomBuildTool.Command
- VC.Project.VCCustomBuildTool.CommandLine
- VC.Project.VCCustomBuildTool.AdditionalDependencies
- VC.Project.VCCustomBuildTool.Message
- VC.Project.VCCustomBuildTool.CustomBuildToolAfterTargets
- VC.Project.VCCustomBuildTool.Description
- VC.Project.VCCustomBuildTool.AdditionalInputs
helpviewer_keywords:
- build tools (C++), specifying
- custom build tools (C++), specifying
- builds (C++), custom build tools
ms.openlocfilehash: db3162e3f7ad3f007d3f26e1ee2a279e5a132eb9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275340"
---
# <a name="specify-custom-build-tools"></a>Özel derleme araçlarını belirtme

*Özel bir yapı aracı* , derleme sistemine belirli giriş dosyaları oluşturmak için gereken bilgileri sağlar. Özel bir yapı aracı çalıştırılacak komutu, giriş dosyalarının listesini, komut tarafından oluşturulan çıkış dosyalarının bir listesini ve aracın isteğe bağlı bir açıklamasını belirtir.

Özel derleme araçları ve özel derleme adımları hakkında genel bilgi için bkz. [özel derleme adımlarını anlama ve olayları oluşturma](understanding-custom-build-steps-and-build-events.md).

### <a name="to-specify-a-custom-build-tool"></a>Özel bir yapı aracı belirtmek için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](working-with-project-properties.md).

1. **Yapılandırma kutusunu etkinleştirmek** Için **yapılandırma özellikleri** ' ni seçin. **Yapılandırma** kutusunda, özel yapı aracı belirtmek istediğiniz yapılandırmayı seçin.

1. **Çözüm Gezgini**, özel derleme aracı için giriş dosyasını seçin.

   **Özel derleme aracı** klasörü görünmezse, seçtiğiniz dosyanın dosya uzantısı bir varsayılan araçla ilişkilendirilir. Örneğin,. c ve. cpp dosyaları için varsayılan araç derleyicisidir. Varsayılan bir araç ayarını geçersiz kılmak için, **yapılandırma özellikleri** düğümünde, **genel** klasöründe, **öğe türü** özelliğinde **özel derleme aracı**' nı seçin. **Uygula** ' yı seçin ve **özel derleme aracı** düğümü görüntülenir.

1. **Özel derleme aracı** düğümünde, **genel** klasöründe, özel derleme aracı ile ilişkili özellikleri belirtin:

   - **Ek bağımlılıklar**' da, özel yapı aracı tanımlanmakta olan her türlü ek dosyayı belirtin (özel derleme aracı ile ilişkili dosya, açıkça araca bir girdi olarak kabul edilir). Ek giriş dosyalarının olması özel bir derleme aracı için gerekli değildir. Birden fazla ek giriş varsa, bunları noktalı virgülle ayırın.

      Ek bir **Bağımlılıklar** dosyasının tarihi giriş dosyasından daha sonra ise, özel derleme aracı çalıştırılır. **Ek bağımlılıklar** dosyalarının tümü giriş dosyasından eskiyse ve giriş dosyası **çıktılar** Özellik dosyasından eskiyse, özel derleme aracı çalıştırılmaz.

      Örneğin, giriş olarak MyInput. x içeren ve MyInput. x adlı bir özel derleme aracınız olduğunu varsayalım ve MyInput. x, MyHeader. h üstbilgi dosyasını içerir. MyHeader. h ' yi MyInput. x için giriş bağımlılığı olarak belirtebilirsiniz ve derleme sistemi MyInput. x veya MyHeader. h ile ilgili güncel olmadığında MyInput. cpp öğesini oluşturur.

      Giriş bağımlılıkları, özel derleme araçlarınızın ihtiyacınız olan sırada çalışmasını da sağlayabilir. Yukarıdaki örnekte, MyHeader. h ' nin aslında özel bir yapı aracının çıktısı olduğunu varsayalım. MyHeader. h, MyInput. x bağımlılığı olduğundan, derleme sistemi önce MyInput. x üzerinde özel derleme aracını çalıştırmadan önce MyHeader. h öğesini derler.

   - Komut **satırında**, komut isteminde şunu belirtmiş gibi bir komut belirtin. Geçerli bir komut veya toplu iş dosyası ve gerekli giriş veya çıkış dosyalarını belirtin. Sonraki tüm komutların yürütüldüğünü garantilemek için bir toplu iş dosyasının adından önce Batch komutunu **çağır** komutunu belirtin.

      Birden çok giriş ve çıkış dosyası, MSBuild makroları ile sembosel olarak belirtilebilir. Dosyaların konumunu veya dosya kümelerinin adlarını belirtme hakkında bilgi için bkz. [derleme komutları ve özellikleri Için ortak makrolar](reference/common-macros-for-build-commands-and-properties.md).

      '% ' Karakteri MSBuild tarafından ayrıldığından, bir ortam değişkeni belirtirseniz her **%** kaçış karakterini **%25** onaltılık kaçış dizisi ile değiştirin. Örneğin, **% windir%** öğesini **% 25windir %25** ile değiştirin. MSBuild, ortam değişkenine erişmeden önce her **%25** sırayı **%** karakteriyle değiştirir.

   - **Açıklama**' da, bu özel derleme aracı hakkında açıklayıcı bir ileti girin. İleti, derleme sistemi bu aracı işlediğinde **Çıkış** penceresine yazdırılır.

   - **Çıktılar**' de çıkış dosyasının adını belirtin. Bu gerekli bir giriştir; Bu özellik için bir değer olmadan, özel derleme aracı çalıştırılmaz. Özel bir derleme aracında birden fazla çıkış varsa, dosya adlarını noktalı virgülle ayırın.

      Çıkış dosyasının adı, **komut satırı** özelliğinde belirtilen şekilde aynı olmalıdır. Proje derleme sistemi, dosyayı arar ve tarihini kontrol eder. Çıkış dosyası giriş dosyasından eskiyse veya çıkış dosyası bulunamazsa, özel derleme aracı çalıştırılır. **Ek bağımlılıklar** dosyalarının tümü giriş dosyasından eskiyse ve giriş dosyası **çıktılar** özelliğinde belirtilen dosyadan eskiyse, özel derleme aracı çalıştırılmaz.

Yapı sisteminin özel yapı aracı tarafından oluşturulan bir çıkış dosyasında çalışmasını istiyorsanız, onu projeye el ile eklemeniz gerekir. Özel derleme aracı derleme sırasında dosyayı güncelleştirir.

## <a name="example"></a>Örnek

Projenize Parser. l adlı bir dosya eklemek istediğinizi varsayın. Yürütülebilir bir çözümleyiciniz **lexer.exe**. Aynı temel ada (Parser. c) sahip bir. c dosyası üretmek için Parser. l öğesini işlemek üzere kullanmak istiyorsunuz.

İlk olarak, projeye Parser. l ve Parser. c ' yi ekleyin. Dosyalar henüz yoksa dosyalara bir başvuru ekleyin. Parser. l için özel bir derleme aracı oluşturun ve **Commands** özelliğine şunu girin:

> **% sözcük temelli çözümleyici (FullPath). \% (Dosya adı). c**

Bu komut, Parser. l üzerinde sözlü çözümleyici 'yi çalıştırır ve Parser. c çıktılarını proje dizinine çıkarır.

**Çıktılar** özelliğinde, aşağıdakileri girin:

> **.\% (Dosya adı). c**

Projeyi derlediğinizde, derleme sistemi parser. l ve Parser. c zaman damgalarını karşılaştırır. Parser. l daha yeni bir özelliktir veya Parser. c yoksa, derleme sistemi, Parser. c ' yi güncel hale getirmek için **komut satırı** özelliğinin değerini çalıştırır. Parser. c aynı zamanda projeye eklendiğinden, derleme sistemi parser. c ' yi derler.

## <a name="see-also"></a>Ayrıca bkz.

[Derleme komutları ve özellikleri için genel makrolar](reference/common-macros-for-build-commands-and-properties.md)<br>
[Derleme Özelleştirmeleri Sorunlarını Giderme](troubleshooting-build-customizations.md)
