---
description: 'Daha fazla bilgi edinin: Clang bağlayıcı Özellikleri (Android C++)'
title: Clang Bağlayıcısı Özellikleri (Android C++)
ms.date: 10/23/2017
ms.assetid: 66e88848-116c-4eb0-bc57-183394d35b57
f1_keywords:
- VC.Project.VCLinkerTool.Clang.OutputFile
- VC.Project.VCLinkerTool.Clang.Soname
- VC.Project.VCLinkerTool.Clang.ShowProgress
- VC.Project.VCLinkerTool.Clang.Version
- VC.Project.VCLinkerTool.Clang.VerboseOutput
- VC.Project.VCLinkerTool.Clang.IncrementalLink
- VC.Project.VCLinkerTool.Clang.SharedLibrarySearchPath
- VC.Project.VCLinkerTool.Clang.AdditionalLibraryDirectories
- VC.Project.VCLinkerTool.Clang.UnresolvedReferences
- VC.Project.VCLinkerTool.Clang.OptimizeForMemory
- VC.Project.VCLinkerTool.Clang.IgnoreDefaultLibraryNames
- VC.Project.VCLinkerTool.Clang.ForceSymbolReferences
- VC.Project.VCLinkerTool.Clang.ForceFileOutput
- VC.Project.VCLinkerTool.Clang.OmitDebuggerSymbolInformation
- VC.Project.VCLinkerTool.Clang.GenerateMapFile
- VC.Project.VCLinkerTool.Clang.Relocation
- VC.Project.VCLinkerTool.Clang.FunctionBinding
- VC.Project.VCLinkerTool.Clang.NoExecStackRequired
- VC.Project.VCLinkerTool.Clang.WholeArchive
- VC.Project.VCLinkerTool.Clang.AdditionalOptionsPage
- VC.Project.VCLinkerTool.Clang.AdditionalDependencies
- VC.Project.VCLinkerTool.Clang.LibraryDependencies
ms.openlocfilehash: 65cbfb3d77dad3d78d8b343274d0fa65cf3ed457
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319280"
---
# <a name="clang-linker-properties-android-c"></a>Clang bağlayıcı Özellikleri (Android C++)

| Özellik | Açıklama | Seçenekler |
|--|--|--|
| Çıkış dosyası | Seçeneği, bağlayıcının oluşturduğu programın varsayılan adını ve konumunu geçersiz kılar. (-o) |
| Ilerlemeyi göster | Bağlayıcı Ilerleme Iletilerini yazdırır. |
| Sürüm | -Version seçeneği, bağlayıcıya yürütülebilir dosyanın üstbilgisine bir sürüm numarası koymasını söyler. |
| Ayrıntılı çıktıyı etkinleştir | -Verbose seçeneği, bağlayıcıya hata ayıklama için ayrıntılı iletiler çıkışını söyler. |
| Artımlı bağlamayı etkinleştir | Seçeneği bağlayıcıya artımlı bağlamayı etkinleştirmesini söyler. |
| Paylaşılan kitaplık arama yolu | Kullanıcının paylaşılan kitaplık arama yolunu doldurmasına izin verir. |
| Ek kitaplık dizinleri | Kullanıcının ortam kitaplık yolunu geçersiz kılmasına izin verir. (-L klasörü). |
| Çözümlenmemiş sembol başvurularını raporla | Etkin olduğunda bu seçenek çözümlenmemiş sembol başvurularını raporlar. |
| Bellek kullanımı Için iyileştirin | Bellek kullanımı için okuyarak, sembol tablolarını gereken şekilde iyileştirin. |
| Belirli varsayılan kitaplıkları Yoksay | Yoksayılacak bir veya daha fazla varsayılan kitaplık adını belirtir. |
| Sembol başvurularını zorla | Simgenin çıkış dosyasına tanımsız bir sembol olarak girilmesini zorla. |
| Hata ayıklayıcı sembol bilgisi | Çıkış dosyasından hata ayıklayıcı sembol bilgisi. | **Tümünü dahil et**<br /><br />**Yeniden konumlandırma Işlemesi için gereksiz sembolleri atla**<br /><br />**Yalnızca hata ayıklayıcı sembol bilgisini atla**<br /><br />**Tüm sembol bilgilerini atla** |
| Paket hata ayıklayıcı sembol bilgisi | Paketlemeden önce hata ayıklayıcı sembolleri bilgilerini Strip.  Hata ayıklama için özgün ikilinin bir kopyası kullanılır. |
| Eşleme dosyası adı | MAP seçeneği, bağlayıcının Kullanıcı tanımlı ada sahip bir eşleme dosyası oluşturmasını söyler. |
| Yeniden konumlandırmadan sonra değişkenleri ReadOnly olarak işaretle | Bu seçenek, yeniden konumlandırmadan sonra değişkenleri salt okunurdur. |
| Hemen Işlev bağlamayı etkinleştir | Bu seçenek, hemen işlev bağlamasının nesnesini işaretler. |
| Yürütülebilir yığın gerektir | Bu seçenek çıktıyı yürütülebilir yığın gerektirmeyen olarak işaretler. |
| Tüm arşiv | Tüm arşiv kaynaklardaki tüm kodu ve ek bağımlılıkları kullanır. |
| Ek Seçenekler | Ek seçenekler. |
| Ek bağımlılıklar | Bağlantı komut satırına eklenecek ek öğeleri belirtir. |
| Kitaplık bağımlılıkları | Bu seçenek bağlayıcı komut satırına eklenecek ek kitaplıkların belirtilmesine izin verir. Ek kitaplıklar, *LIB* ile başlayan ve *. a* veya *. so* uzantılı bağlayıcı komut satırının sonuna eklenir.  (-lFILE) |
