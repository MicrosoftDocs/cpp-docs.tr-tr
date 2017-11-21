---
title: "Bağlayıcı özellikleri (Linux C++) | Microsoft Docs"
ms.custom: 
ms.date: 9/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0243a94-8164-425b-b2fe-b84ff363d546
author: mikeblome
ms.author: mblome
manager: ghogen
f1_keywords:
- VC.Project.VCLinkerTool.OutputFile
- VC.Project.VCLinkerTool.ShowProgress
- VC.Project.VCLinkerTool.Version
- VC.Project.VCLinkerTool.VerboseOutput
- VC.Project.VCLinkerTool.UnresolvedReferences
- VC.Project.VCLinkerTool.OptimizeForMemory
- VC.Project.VCLinkerTool.SharedLibrarySearchPath
- VC.Project.VCLinkerTool.AdditionalLibraryDirectories
- VC.Project.VCConfiguration.BuildLogFile
- VC.Project.VCLinkerTool.IgnoreDefaultLibraryNames
- VC.Project.VCLinkerTool.ForceSymbolReferences
- VC.Project.VCLinkerTool.LibraryDependencies
- VC.Project.VCLinkerTool.ForceFileOutput
- VC.Project.VCLinkerTool.GenerateMapFile
- VC.Project.VCLinkerTool.Relocation
- VC.Project.VCLinkerTool.FunctionBinding
- VC.Project.VCLinkerTool.NoExecStackRequired
- VC.Project.WholeArchive
- VC.Project.AdditionalOptionsPage
- VC.Project.VCLinkerTool.AdditionalDependencies
ms.openlocfilehash: 963d73e73e42930f0245c0fef443da27bf451bc6
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="linker-properties-linux-c"></a>Bağlayıcı özellikleri (Linux C++)

## <a name="general"></a>Genel
Özellik | Açıklama | Seçenekler
--- | ---| ---
Çıkış dosyası | Varsayılan ad ve konum bağlayıcı oluşturur programın seçeneğini geçersiz kılar. (-o).
İlerlemesini Göster | Bağlayıcı ilerleme iletilerini yazdırır.
Sürüm | Sürüm seçenek yürütülebilir dosya üstbilgisinde bir sürüm numarası koymak için bağlayıcı söyler.
Ayrıntılı çıktı etkinleştir | Verbose seçenek hata ayıklama için ayrıntılı ileti çıkışı için bağlayıcı söyler.
İzleme | İzleme seçeneği işlendikçe girdi dosyaları çıkarmak için bağlayıcı söyler.
İzleme simgeleri | Bir simge göründüğü dosyaların listesini yazdırma. (--izleme simgesi simgesi =)
Yazdırma eşleme | Yazdırma eşleme seçeneği belirten bir bağlantı harita çıktısını almak için bağlayıcı.
Çözümlenmemiş simge başvurularını raporu | Bu seçenek etkinleştirildiğinde çözümlenmemiş sembol başvuruları bildirir.
Bellek kullanımı için en iyi duruma getirme | Sembol tabloları gerektiği gibi yeniden okumaya bellek kullanımı için en iyi duruma getirme.
Paylaşılan kitaplık arama yolu | Paylaşılan kitaplık arama yolu doldurmak olanak tanır. (- rpath - bağlantı yolu =)
Ek Kitaplık dizinleri | Ortam Kitaplığı yol geçersiz kılmanıza olanak tanır. (-M klasörü).
Bağlayıcı | Programın sırasında bağlama veya uzak sistem üzerindeki bağlayıcı yolunu çağırma belirtir.
Bağlantı zaman aşımı | Milisaniye cinsinden zaman aşımı bağlama uzaktan.
Kopya çıktı | Derleme çıktı dosyası Uzak sistemden yerel makineye kopyalanıp kopyalanmayacağını belirtir.

## <a name="input"></a>Giriş
Özellik | Açıklama | Seçenekler
--- | ---| ---
Belirli varsayılan kitaplıkları yoksay | Bir veya daha fazla yok saymak için varsayılan kitaplık adını belirtir. (--dışlama kitaplıklar lib, lib)
Varsayılan kitaplıklar yoksay | Varsayılan kitaplıklar yoksay ve yalnızca belirtilen kitaplıkları explicitely arayın.
Tanımsız simge başvurularını zorla | Tanımlanmamış bir simge olarak çıktı dosyasında girilecek simgesi zorlar. (- u simgesi--tanımsız simgesi =)
Kitaplık bağımlılıkları | Bu seçenek bağlayıcı komut satırına eklenecek ek kitaplıklarını belirtme sağlar. Ek Kitaplığı 'lib' ve 'bir' uzantısı ile biten önekli bağlayıcı komut satırının sonuna eklenir.  (-lFILE)
Ek Bağımlılıklar | Bağlantı komut satırına eklenecek ek öğelerini belirtir.

## <a name="debugging"></a>Hata Ayıklama
Özellik | Açıklama | Seçenekler
--- | ---| ---
Hata ayıklayıcı sembol bilgileri | Sembol bilgilerini çıktı dosyası hata ayıklayıcı. | **Tüm içerir**<br>**Hata ayıklayıcı sembol bilgileri yalnızca atlayın**<br>**Tüm simge bilgilerini atlayın**<br>
Dosya adı eşleme | Map seçeneği kullanıcı belirtilen ada sahip bir harita dosyası oluşturmak için bağlayıcı söyler. (-Harita =)

## <a name="advanced"></a>Gelişmiş
Özellik | Açıklama | Seçenekler
--- | ---| ---
Yeniden konumlandırma sonra işareti değişkenleri salt okunur | Bu seçenek, sonra yeniden konumlandırma değişkenleri salt okunur işaretler.
Hemen işlev bağlama etkinleştir | Bu seçenek nesne hemen işlev bağlama için işaretler.
Yürütülebilir yığını gerektirmez | Bu seçenek çıktı yürütülebilir yığını gerektirmeyen olarak işaretler.
Tüm arşiv | Tüm arşiv kaynakları ve ek bağımlılıklar tüm koddan kullanır.


## <a name="additional-options"></a>Ek Seçenekler



