---
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
ms.openlocfilehash: dbce226b34503a9e8e70b6f19d9aa0c68ef487f3
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57824155"
---
# <a name="specify-custom-build-tools"></a>Özel derleme araçlarını belirtme

A *özel derleme aracı* yapı sistemini belirli giriş dosyası oluşturmak için ihtiyaç duyduğu bilgileri sağlar. Özel derleme aracı çalıştırmak için bir komutu, giriş dosyaları listesini, komutu tarafından oluşturulan çıkış dosyaları listesini ve aracının isteğe bağlı bir açıklama belirtir.

Özel derleme araçları ve özel yapı adımları hakkında genel bilgi için bkz. [anlama özel derleme adımlarını ve derleme olayları](understanding-custom-build-steps-and-build-events.md).

### <a name="to-specify-a-custom-build-tool"></a>Özel derleme aracı belirtmek için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** etkinleştirmek için **yapılandırma** kutusu. İçinde **yapılandırma** kutusunda, özel derleme aracı belirtmek istediğiniz yapılandırmayı seçin.

1. İçinde **Çözüm Gezgini**, özel derleme aracı için giriş dosyası seçin.

   Varsa **özel derleme aracı** görünmez, seçtiğiniz dosyanın dosya uzantısı varsayılan aracı ile ilişkilidir. Örneğin, varsayılan .c ve .cpp dosyaları için derleyici aracıdır. İçinde bir varsayılan aracı ayarını geçersiz kılmak için **yapılandırma özellikleri** düğümü, **genel** klasörü içinde **öğesi türü** özelliği seçin **özel derleme Aracı**. Seçin **Uygula** ve **özel derleme aracı** düğümünde görüntülenir.

1. İçinde **özel derleme aracı** düğümü, **genel** klasöründe özel ile ilişkili özellikleri derleme aracı belirtin:

   - İçinde **ek bağımlılıklar**, ek dosyaları için özel derleme aracı tanımlanan bir ötesinde belirtin (özel derleme aracı ile ilişkili dosya örtük olarak aracı için girdi olarak kabul edilir). Ek giriş dosyalarını sahip bir özel derleme aracı için bir gereksinim değildir. Birden fazla ek giriş varsa, bunları noktalı virgülle ayırın.

      Varsa bir **ek bağımlılıklar** dosyanın tarihtir giriş dosyasından daha sonra özel derleme aracı çalıştırın. Tüm, **ek bağımlılıklar** dosyalarıdır giriş dosyasından daha eski ve giriş dosyası şundan **çıkışları** özellik dosyası, ardından özel derleme aracı çalışmıyor.

      Örneğin, MyInput.x girdi olarak alır ve MyInput.cpp ve MyInput.x MyHeader.h bir üstbilgi dosyası içeren bir özel derleme aracı olduğunu varsayalım. Derleme Sistemi MyInput.x veya MyHeader.h güncel olmadığında MyInput.cpp derler ve MyInput.x için Giriş bir bağımlılık olarak MyHeader.h belirtebilirsiniz.

      Giriş bağımlılıkları, ayrıca, özel derleme araçları ihtiyacınız sırayla çalıştırmak emin olabilirsiniz. Önceki örnekte MyHeader.h aslında özel derleme aracı çıktısını olduğunu varsayın. MyHeader.h MyInput.x bir bağımlılığı olduğundan, derleme sistemi ilk Myheader.h MyInput.x özel derleme Aracı'nı çalıştırmadan önce oluşturacaksınız.

   - İçinde **komut satırı**, komut isteminde belirtme gibi bir komutu belirtin. Geçerli komut veya toplu iş dosyasını belirtin ve tüm gerekli giriş veya çıkış dosyalarını. Belirtin **çağrı** toplu tüm komutlar yürütülür garanti etmek için önce bir toplu iş dosyası adını komutu.

      Birden çok giriş ve çıkış dosyalarının bildirmelerine MSBuild makroları ile belirtilebilir. Dosyalarının konumu veya dosya kümelerini adlarını belirtme hakkında daha fazla bilgi için bkz: [derleme komutları ve özellikler için ortak makroları](reference/common-macros-for-build-commands-and-properties.md).

      Her bir ortam değişkenini Değiştir belirtirseniz, '%' karakter MSBuild tarafından ayrılmış olduğundan **%** kaçış karakteriyle **% 25** onaltılı çıkış dizisi. Örneğin, **% WINDIR %** ile **25WINDIR % 25**. MSBuild değiştirir her **% 25** ile sıralı **%** ortam değişkenini erişmeden önce karakter.

   - İçinde **açıklama**, bu özel derleme aracı hakkında açıklayıcı bir ileti girin. İleti yazdırıldığında **çıkış** derleme sistemi, bu aracı işlediğinde penceresi.

   - İçinde **çıkışları**, çıktı dosyası adını belirtin. Bu gerekli bir giriştir; Özel derleme aracı bu özellik için bir değer olmadan çalışmaz. Özel derleme aracı birden çok çıkış varsa, dosya adları noktalı virgül ile ayırın.

      İçinde belirtilen gibi çıkış dosyasının adı aynı olmalıdır **komut satırı** özelliği. Proje derleme sistemi dosyasını arayın ve kendi tarihini denetleyin. Çıkış dosyası giriş dosyasından daha eski ise veya çıktı dosyası bulunamazsa, özel derleme aracı çalıştırılır. Tüm, **ek bağımlılıklar** dosyalarıdır giriş dosyasından daha eski ve giriş dosyası içinde belirtilen dosya daha eski **çıkışları** özelliği özel derleme aracı değil çalıştırın.

Özel derleme aracı tarafından oluşturulan bir çıktı dosyası üzerinde çalışılacak yapı sistemini istiyorsanız, bunu el ile projeye eklemeniz gerekir. Özel derleme aracı, derleme sırasında dosyasını güncelleştirir.

## <a name="example"></a>Örnek

Projenizdeki parser.l adlı bir dosya eklemek istediğinizi varsayalım. Bir sözcük temelli çözümleyici sahip **lexer.exe**, üzerinde yürütülebilir dosya yolu. Aynı temel ada (parser.c) sahip bir .c dosyası üretmek için parser.l işlemek için kullanmak istediğiniz.

İlk olarak, parser.l ve parser.c projeye ekleyin. Dosyaları henüz mevcut değilse, dosyalar bir başvuru ekleyin. Özel derleme aracı için parser.l oluşturun ve aşağıdaki **komutları** özelliği:

> **sözcük temelli çözümleyici %(FullPath). \%.C (Filename)**

Bu komut, sözcük temelli çözümleyici parser.l üzerinde çalışır ve proje dizininin parser.c çıkarır.

İçinde **çıkışları** özelliği, aşağıdakileri girin:

> **. \%.C (Filename)**

Projeyi derlerken, derleme sistemi parser.l parser.c ve zaman damgaları karşılaştırır. Parser.l ise daha yeni veya parser.c yoksa, derleme sistemi değerini çalışan **komut satırı** parser.c güncel duruma getirmek için özellik. Parser.c da projeye eklendikten sonra derleme sistemi, ardından parser.c derler.

## <a name="see-also"></a>Ayrıca bkz.

[Genel derleme komutları ve Özellikler makroları](reference/common-macros-for-build-commands-and-properties.md)<br>
[Derleme Özelleştirmeleri Sorunlarını Giderme](troubleshooting-build-customizations.md)
