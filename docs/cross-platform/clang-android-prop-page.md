---
title: Clang Projesi Özellikleri (Android C++)
ms.date: 10/23/2017
ms.assetid: 663140ea-a568-472b-a79a-dfea8818e06a
f1_keywords:
- VC.Project.VCClangCompilerTool.AdditionalIncludeDirectories
- VC.Project.VCClangCompilerTool.DebugInformationFormat
- VC.Project.VCClangCompilerTool.ObjectFile
- VC.Project.VCClangCompilerTool.WarningLevel
- VC.Project.VCClangCompilerTool.WarnAsError
- VC.Project.VCClangCompilerTool.Verbose
- VC.Project.VCClangCompilerTool.Optimization
- VC.Project.VCClangCompilerTool.StrictAliasing
- VC.Project.VCClangCompilerTool.OmitFramePointers
- VC.Project.VCClangCompilerTool.ExceptionHandling
- VC.Project.VCClangCompilerTool.EnableFunctionLevelLinking
- VC.Project.VCClangCompilerTool.DataLevelLinking
- VC.Project.VCClangCompilerTool.DataLevelLinking
- VC.Project.VCClangCompilerTool.FloatABI
- VC.Project.VCClangCompilerTool.BufferSecurityCheck
- VC.Project.VCClangCompilerTool.PIC
- VC.Project.VCClangCompilerTool.UseShortEnums
- VC.Project.VCClangCompilerTool.RuntimeTypeInfo
- VC.Project.VCClangCompilerTool.CLanguageStandard
- VC.Project.VCClangCompilerTool.CppLanguageStandard
- VC.Project.VCClangCompilerTool.PreprocessorDefinitions
- VC.Project.VCClangCompilerTool.UndefinePreprocessorDefinitions
- VC.Project.VCClangCompilerTool.UndefineAllPreprocessorDefinitions
- VC.Project.VCClangCompilerTool.ShowIncludes
- VC.Project.VCClangCompilerTool.PrecompiledHeader
- VC.Project.VCClangCompilerTool.PrecompiledHeaderFile
- VC.Project.VCClangCompilerTool.PrecompiledHeaderOutputFileDirectory
- VC.Project.VCClangCompilerTool.PrecompiledHeaderCompileAs
- VC.Project.VCClangCompilerTool.CompileAs
- VC.Project.VCClangCompilerTool.ForcedIncludeFiles
- VC.Project.VCClangCompilerTool.MultiProcessorCompilation
- VC.Project.VCClangCompilerTool.AdditionalOptionsPage
ms.openlocfilehash: 11e8a7f1ea264b26b9092d4834525541e098a5e1
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79444977"
---
# <a name="clang-project-properties-android-c"></a>Clang proje özellikleri (Android C++)

| Özellik | Açıklama | Yapabileceği |
|--|--|--|
| Ek Içerme dizinleri | Ekleme yoluna eklenecek bir veya daha fazla dizin belirtir; birden fazlaysa noktalı virgülle ayırın. (-I*yolu*). |
| Hata ayıklama bilgi biçimi | Derleyici tarafından oluşturulan hata ayıklama bilgilerinin türünü belirtir. | **Hiçbiri** -hata ayıklama bilgisi üretmez, bu nedenle derleme daha hızlı olabilir.<br>**Tam hata ayıklama bilgileri (DWARF2)** -DWARF2 hata ayıklama bilgileri oluştur.<br>**Satır numarası bilgisi** -yalnızca satır numarası bilgisi oluştur.<br> |
| Nesne dosyası adı | Varsayılan nesne dosyası adını geçersiz kılacak bir ad belirtir; dosya veya dizin adı olabilir. (/FO*ad*). |
| Uyarı düzeyi | Derleyicinin kod hataları hakkında ne kadar sıkı olmasını istediğinizi seçin.  Diğer bayraklar doğrudan ek seçeneklere eklenmelidir. (/w,/Weverything). | **Tüm uyarıları** kapat-tüm derleyici uyarılarını devre dışı bırakır.<br>**Enablealluyarılar** -varsayılan olarak devre dışı bırakılmış tüm uyarıları etkin şekilde sunar.<br> |
| Uyarıları hata olarak değerlendir | Tüm derleyici uyarılarını hata olarak değerlendirir. Yeni bir proje için tüm derlemelerde/WX kullanılması en iyi yöntem olabilir; Tüm uyarıların çözümlenmesi, en az olası bulma kod kusurlarını güvence altına alacak. |
| Ayrıntılı modu etkinleştir | Çalıştırılacak komutları göster ve ayrıntılı çıkış kullan. |
| İyileştirme | Uygulamanın en iyi duruma getirme düzeyini belirtir. | **Özel** -özel iyileştirme.<br>**Devre dışı** -iyileştirmeyi devre dışı bırak.<br>**Boyutu en aza indirir** -boyut için iyileştirin.<br>**En yüksek hız** -hız için iyileştirin.<br>**Tam iyileştirme** maliyetli iyileştirmeler.<br> |
| Katı diğer ad | En katı diğer ad kurallarını varsayın.  Tek bir türdeki nesne, farklı bir tür nesnesiyle aynı adreste değil hiçbir zaman kabul değildir. |
| Çerçeve Işaretçisini atla | Çağrı yığınında çerçeve işaretçilerinin oluşturulmasını engeller. |
| Özel C++ durumları etkinleştir | Derleyici tarafından kullanılacak özel durum işleme modelini belirtir. | **Hayır** -özel durum işlemeyi devre dışı bırak.<br>**Evet** -özel durum işlemeyi etkinleştir.<br>**Geriye doğru tablolar** -gereken statik verileri oluşturur, ancak oluşturulan kodu etkilemez.<br> |
| Işlev düzeyinde bağlamayı etkinleştir | Derleyicinin paketlenmiş işlevler (Compts) biçiminde tek tek işlevleri paketetmesine olanak tanır. Düzenle ve çalışmaya devam etmek için gereklidir.     (ffunction-sections). |
| Veri düzeyinde bağlamayı etkinleştir | Her veri öğesini ayrı bir bölümde yayarak kullanılmayan verileri kaldırmak için bağlayıcı iyileştirmelerini sağlar. |
| Gelişmiş SıMD 'yi (neon) etkinleştir | NEON kayan nokta donanımı için kod oluşturmayı mümkün bir şekilde sunar. Yalnızca ARM mimarisi için geçerlidir. |
| Kayan nokta ABı | Kayan nokta ABı seçmek için seçim seçeneği. | **Soft** -' Soft ', derleyicinin kayan nokta işlemleri için kitaplık çağrıları içeren çıkış oluşturmasına neden olur.<br>**Softfp** -' softfp ', donanım kayan nokta yönergeleri kullanılarak kod oluşturulmasına izin verir, ancak yine de yumuşak float çağırma kurallarını kullanır.<br>**Hard** -' Hard ', kayan nokta yönergelerinin oluşturulmasına izin verir ve FPU 'ya özgü çağırma kuralları kullanır.<br> |
| Güvenlik denetimi | Güvenlik denetimi, bir programın güvenliği üzerinde yaygın olarak gerçekleştirilen bir saldırıya karşı yığın arabelleğinin çalıştırılmaların algılanmasına yardımcı olur. (fstack-Protector). | **Güvenlik denetimini devre** dışı bırak-güvenlik denetimini devre dışı bırak.<br>**Güvenlik denetimini etkinleştirin** -güvenlik denetimini etkinleştirin. (fstack-Protector)<br> |
| Konumdan bağımsız kod | Paylaşılan bir kitaplıkta kullanılmak üzere konumdan bağımsız kod (PIC) üretin. |
| Kısa sabit listeleri kullan | Sabit listesi türü, yalnızca olası değerlerin giriş kümesi için gereken sayıda bayt kullanır. |
| Çalışma zamanı türü bilgilerini etkinleştir | Çalışma zamanında nesne türlerini C++ denetlemek için kod ekler (çalışma zamanı türü bilgileri).     (frtti, FNO-rtti) |
| C dil standardı | C dil standardını belirler. | **Varsayılan**<br>**C89** -c89 dil standardı.<br>**C99** -C99 dil standardı.<br>**C11** -C11 dil standardı.<br>**C99 (GNU diyalekti)** -C99 (GNU diyalekti) dil standardı.<br>**C11 (GNU diyalekti)** -C11 (GNU diyalekti) dil standardı.<br> |
| C++Dil standardı | C++ Dil standardını belirler. | **Varsayılan**<br>**C++ 03** -C++ 03 dil standardı.<br>**C++ 11** -C++ 11 dil standardı.<br>**C++ 14** -C++ 14 dil standardı.<br>**C++ 03 (GNU diyalekti)** -c++ 03 (GNU diyalekti) dil standardı.<br>**C++ 11 (GNU diyalekti)** -c++ 11 (GNU diyalekti) dil standardı.<br>**C++ 14 (GNU diyalekti)** -c++ 14 (GNU diyalekti) dil standardı.<br> |
| Önişlemci tanımları | Kaynak dosyanız için ön işleme sembollerini tanımlar. (-D) |
| Önişlemci tanımlarının tanımı kaldırılıyor | Ön işlemci için bir veya daha fazla tanımlana izlemeyi belirtir.  (-U *makrosu*) |
| Tüm önişlemci tanımlarının tanımlanunlarını kaldır | Önceden tanımlanmış tüm Önişlemci değerlerini tanımlayın.  (-undef) |
| Eklemeleri göster | Derleyici çıkışı içeren ekleme dosyalarının bir listesini oluşturur.  (-H) |
| Ön derlenmiş üstbilgi | Önceden derlenmiş üst bilgi oluştur/kullan: derleme sırasında önceden derlenmiş üst bilgi oluşturmayı veya kullanmayı mümkün. | **Use** -önceden derlenmiş üst bilgi kullanın.<br>Önceden derlenmiş üst **bilgiler kullanılmıyor** -önceden derlenmiş üst bilgi kullanılmıyor.<br> |
| Önceden derlenmiş üst bilgi dosyası | Önceden derlenmiş üstbilgi dosyası için kullanılacak üst bilgi dosyası adını belirtir. Bu dosya, derleme sırasında ' zorunlu Içerme dosyaları ' öğesine de eklenir |
| Ön derlenmiş üst bilgi çıkış dosyası dizini | Oluşturulan ön derlenmiş üstbilgi için dizini belirtir. Bu dizin, derleme sırasında ' ek Içerme dizinleri 'ne de eklenir |
| Ön derlenmiş üstbilgiyi şu şekilde derle | Önceden derlenmiş üstbilgi dosyası için derleme dil seçeneğini belirleyin (-x c-Header,-x c++-header). | **C** kodu olarak derle-c kodu olarak derleyin.<br>**Kod C++ olarak** C++ derle-kod olarak derle.<br> |
| Farklı derle | *`.c`* ve *`.cpp`* dosyaları için derleme dil seçeneğini belirleyin.  ' Default ', *`.c`* veya *`.cpp`* uzantısına göre algılanır. (-x c, -x c++) | **Varsayılan** -varsayılan.<br>**C** kodu olarak derle-c kodu olarak derleyin.<br>**Kod C++ olarak** C++ derle-kod olarak derle.<br> |
| Zorunlu Içerme dosyaları | bir veya daha fazla zorunlu ekleme dosyası.     (-include *adı*) |
| Çok işlemcili derleme | Çok işlemcili derleme. |
| Ek Seçenekler | Ek seçenekler. |
