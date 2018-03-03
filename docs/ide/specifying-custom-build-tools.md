---
title: "Derleme araçlarını özel belirtme | Microsoft Docs"
ms.custom: 
ms.date: 12/28/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs:
- C++
helpviewer_keywords:
- build tools (C++), specifying
- custom build tools (C++), specifying
- builds (C++), custom build tools
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4edd3b1fdb2b6d09be6f5fcd9a6c9d08ba7a6994
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
---
# <a name="specify-custom-build-tools"></a>Özel derleme araçlarını belirtme

A *özel derleme aracı* yapılandırma sistemi belirli giriş dosyaları oluşturmak gereken bilgileri sağlar. Özel derleme aracı çalıştırılacak komutu, giriş dosyaların bir listesini, komutu tarafından oluşturulan çıkış dosyaları listesini ve aracı için isteğe bağlı bir açıklama belirtir.

Özel derleme adımları ve özel derleme araçları hakkında genel bilgi için bkz: [anlama özel derleme adımlarını ve derleme olaylarını](../ide/understanding-custom-build-steps-and-build-events.md).

### <a name="to-specify-a-custom-build-tool"></a>Özel derleme aracı belirtmek için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için bkz: [Visual C++ proje özelliklerini ayarlama](../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** etkinleştirmek için **yapılandırma** kutusu. İçinde **yapılandırma** kutusunda, bir özel derleme aracı belirtmek istediğiniz yapılandırma seçin.

1. İçinde **Çözüm Gezgini**, giriş dosyası için özel yapı Aracı'nı seçin.

   Varsa **özel yapı aracı** klasörü görünmez, seçtiğiniz dosyanın dosya uzantısını varsayılan aracı ile ilişkilidir. Örneğin, varsayılan .c ve .cpp dosyaları için derleyici aracıdır. İçinde bir varsayılan aracı ayarını geçersiz kılmak için **yapılandırma özellikleri** düğümü, **genel** klasörü içinde **öğesi türü** özelliği seçin **özel derleme Aracı**. Seçin **Uygula** ve **özel yapı aracı** düğümünde görüntülenir.

1. İçinde **özel yapı aracı** düğümü, **genel** klasörünü, özel ile ilişkili özellikleri yapı aracı belirtin:

   - İçinde **ek bağımlılıklar**, için özel yapı aracı tanımlanmış bir ötesinde ek dosyalardan belirtin (özel derleme aracı ile ilişkili dosya örtük olarak aracına bir girdi olarak kabul edilir). Ek giriş dosyaları sahip bir özel derleme aracı için zorunlu değildir. Birden fazla ek giriş varsa, bunları noktalı virgülle ayırın.

      Varsa bir **ek bağımlılıklar** dosyanın tarihidir giriş dosyası'den daha sonra özel derleme aracını çalıştırın. Tüm, **ek bağımlılıklar** giriş dosyasından daha eski olan dosyalar ve giriş dosyası daha eski **çıkışları** özellik dosyası sonra özel derleme aracı çalışmıyor.

      Örneğin, MyInput.x giriş olarak alır ve oluşturur MyInput.cpp ve MyInput.x MyHeader.h bir üstbilgi dosyası içeren bir özel derleme aracı olduğunu varsayalım. MyInput.x için Giriş bir bağımlılık olarak MyHeader.h belirtebilirsiniz ve MyInput.x veya MyHeader.h göre güncel olmadığında yapı sistem MyInput.cpp oluşturacaksınız.

      Giriş bağımlılıkları, ayrıca, özel derleme araçları için gereksinim duyarsınız sırayla çalıştırmak emin olabilirsiniz. Önceki örnekte MyHeader.h gerçekten özel derleme aracın çıktısının olduğunu varsayın. MyHeader.h MyInput.x bir bağımlılığı olduğundan, yapı sistem ilk Myheader.h MyInput.x üzerinde özel derleme Aracı'nı çalıştırmadan önce oluşturacaksınız.

   - İçinde **komut satırı**, komut isteminde belirtme gibi bir komutu belirtin. Geçerli bir komut veya toplu iş dosyasını belirtin ve gerekli giriş veya çıkış dosyaları. Belirtin **çağrısı** toplu tüm komutlar yürütülür güvence altına almak için bir toplu iş dosyası adından önce komutu.

      Birden çok girdi ve çıktı dosyası sembolik olarak MSBuild makroları ile belirtilebilir. Dosyalarının konumu veya dosya kümelerini adlarını belirtme hakkında daha fazla bilgi için bkz: [derleme komutları ve özellikler için ortak makrolar](../ide/common-macros-for-build-commands-and-properties.md).

      Bir ortam değişkeni yerine her belirtirseniz, '%' karakteri MSBuild tarafından ayrılmış olduğundan  **%**  kaçış karakteri ile **% 25** onaltılık çıkış dizisi. Örneğin, **% WINDIR %** ile **25WINDIR % 25**. MSBuild değiştirir her **% 25** ile sıra  **%**  ortam değişkeni erişim izni vermeden önce karakter.

   - İçinde **açıklama**, bu özel derleme aracı ilgili açıklayıcı bir ileti girin. İleti için yazdırılır **çıkış** yapı sistem bu aracı işlerken penceresi.

   - İçinde **çıkışları**, çıktı dosyası adını belirtin. Bu gerekli bir giriştir; Bu özellik için bir değer özel derleme araç çalışmaz. Özel derleme aracı birden çok çıktı varsa, dosya adları noktalı virgülle ayırın.

      İçinde belirtilen çıkış dosyasının adı aynı olmalıdır **komut satırı** özelliği. Proje derleme sistem dosyasını arayın ve kendi tarihini denetleyin. Çıktı dosyası giriş dosyadan daha yeni veya çıktı dosyası bulunmazsa, özel derleme Aracı'nı çalıştırın. Tüm, **ek bağımlılıklar** giriş dosyasından daha eski olan dosyalar ve giriş dosyası belirtilen dosyadan daha eski **çıkışları** özelliği, özel derleme aracın çalıştığı değil.

Özel derleme aracı tarafından oluşturulan bir çıktı dosyası üzerinde çalışılacak yapı sistem istiyorsanız, el ile projeye eklemelisiniz. Özel derleme aracı dosyasını sırasında derleme güncelleştirir.

## <a name="example"></a>Örnek

Projenizdeki parser.l adlı bir dosya eklemek istediğinizi varsayalım. Bir sözcük Çözümleyicisi sahip **lexer.exe**, yürütülebilir dosya yolu üzerinde. Aynı taban adına (parser.c) sahip bir .c dosyası üretmek için parser.l işlemek için kullanmak istediğiniz.

İlk olarak, parser.l ve parser.c projeye ekleyin. Dosyaları henüz yoksa, dosyaları bir başvuru ekleyin. Özel derleme aracı parser.l için oluşturun ve aşağıdakileri girin **komutları** özelliği:

> **lexer %(FullPath). \%(Dosya adı) .c**

Bu komut, sözcük Çözümleyicisi parser.l üzerinde çalıştırır ve proje dizinine parser.c çıkarır.

İçinde **çıkışları** özelliği, aşağıdakileri girin:

> **. \%(Dosya adı) .c**

Projesi derlerken, derleme sistem parser.l ve parser.c damgalarının karşılaştırır. Parser.l ise daha yeni veya parser.c yoksa, yapı sistem değerini çalıştırdığında **komut satırı** parser.c güncel duruma getirmek için özellik. Parser.c da projeye eklendikten sonra yapı sistem parser.c sonra derler.

## <a name="see-also"></a>Ayrıca bkz.

[Genel Derleme Komutları ve Özellikler Makroları](../ide/common-macros-for-build-commands-and-properties.md)  
[Derleme Özelleştirmeleri Sorunlarını Giderme](../ide/troubleshooting-build-customizations.md)  
