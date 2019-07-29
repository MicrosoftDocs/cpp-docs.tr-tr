---
title: HLSL Özellik Sayfaları
ms.date: 07/24/2019
ms.assetid: 0c65f5ec-a2a5-4f5b-8d4c-fa57113a5a1d
f1_keywords:
- VC.Project.FXCompilerTool.AdditionalIncludeDirectories
- VC.Project.FXCompilerTool.SuppressStartupBanner
- VC.Project.FXCompilerTool.EntryPointName
- VC.Project.FXCompilerTool.TreatWarningAsError
- VC.Project.FXCompilerTool.DisableOptimizations
- VC.Project.FXCompilerTool.EnableDebuggingInformation
- VC.Project.FXCompilerTool.ShaderType
- VC.Project.FXCompilerTool.ShaderModel
- VC.Project.FXCompilerTool.AllResourcesBound
- VC.Project.FXCompilerTool.EnableUnboundedDescriptorTables
- VC.Project.FXCompilerTool.SetRootSignature
- VC.Project.FXCompilerTool.PreprocessorDefinitions
- VC.Project.FXCompilerTool.AdditionalOptionsPage
- VC.Project.FXCompilerTool.VariableName
- VC.Project.FXCompilerTool.HeaderFileOutput
- VC.Project.FXCompilerTool.ObjectFileOutput
- VC.Project.FXCompilerTool.AssemblerOutput
- VC.Project.FXCompilerTool.AssemblerOutputFile
- VC.Project.FXCompilerTool.CompileD2DCustomEffect
- VC.Project.FXCompilerTool.MultiProcFXC
ms.openlocfilehash: a45ae433e5adaa8aeaf32215d4af7ad0a247af04
ms.sourcegitcommit: 720b74dddb1cdf4e570d55103158304ee1df81f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/29/2019
ms.locfileid: "68606405"
---
# <a name="hlsl-compiler-property-pages"></a>HLSL derleyici Özellik sayfaları

HLSL derleyicisi (fxc. exe) özellik sayfalarını, tek tek HLSL gölgelendirici dosyalarının nasıl oluşturulduğunu yapılandırmak için kullanabilirsiniz. Ayrıca, **komut satırı** özellik sayfasındaki **ek seçenekler** özelliğini kullanarak HLSL derleyicisine komut satırı bağımsız değişkenleri belirtebilirsiniz; Bu, HLSL Özellik sayfalarının diğer özellikleri kullanılarak yapılandırılanmakta olan bağımsız değişkenleri içerir. HLSL derleyicisi hakkında daha fazla bilgi için bkz. [efekt-derleyici aracı](https://go.microsoft.com/fwlink/p/?LinkID=258285&clcid=0x409)

## <a name="hlsl-general-property-page"></a>HLSL genel özellik sayfası

### <a name="additional-include-directories"></a>Ek Içerme dizinleri

Ekleme yoluna eklenecek bir veya daha fazla dizin belirtir; birden fazlaysa noktalı virgülle ayırın. (/I [yol])

### <a name="entrypoint-name"></a>Giriş noktası adı

Gölgelendirici için giriş noktasının adını belirtir (/E [ad])

### <a name="disable-optimizations"></a>Iyileştirmeleri devre dışı bırak

İyileştirmeleri devre dışı bırakmak için **Evet (/OD)** ; Aksi takdirde, **Hayır**. Varsayılan olarak, **hata ayıklama** yapılandırmalarına yönelik değer **Evet (/OD)** ve **Sürüm** yapılandırması için **Hayır** ' dır.

HLSL derleyicisine yönelik **/od** komut satırı bağımsız değişkeni, **/Gfp** komut satırı bağımsız değişkenini örtülü olarak uygular, ancak hem **/od** hem de **/Gfp** komut satırı bağımsız değişkenlerini geçirerek üretilen çıktıyla aynı olamaz işlem.

### <a name="enable-debugging-information"></a>Hata ayıklama bilgilerini etkinleştir

Hata ayıklama bilgilerini etkinleştirmek için **Evet (/Zi)** ; Aksi takdirde, **Hayır**. Varsayılan olarak, **hata ayıklama** yapılandırmalarının değeri **Evet (/Zi)** , **Sürüm** yapılandırması için **Hayır** ' dır.

### <a name="shader-type"></a>Gölgelendirici türü

Gölgelendirici türünü belirtir. Farklı tür gölgelendiriciler grafik işlem hattının farklı parçalarını uygular. Belirli tür gölgelendiriciler yalnızca daha yeni gölgelendirici modellerinde kullanılabilir ( **gölgelendirici modeli** özelliği tarafından belirtilir) — Örneğin, bilgi işlem gölgelendiricileri gölgelendirici modeli 5 ' te sunulmuştur.

Bu özellik, HLSL derleyicisine  **\[/t Type] _\[model]** komut satırı bağımsız değişkeninin  **\[Type]** bölümüne karşılık gelir. **Gölgelendirici modelleri** özelliği, bağımsız değişkenin **[Model]** bölümünü belirtir.

**Yapabileceği**

- **Etki**
- **Köşe gölgelendiricisi**
- **Piksel gölgelendiricisi**
- **Geometri gölgelendiricisi**
- **Hull gölgelendiricisi**
- **Etki alanı gölgelendiricisi**
- **Bilgi işlem gölgelendiricisi**
- **Kitaplık**
- **Kök Imza nesnesi oluştur**

### <a name="shader-model"></a>Gölgelendirici modeli

Gölgelendirici modelini belirtir. Farklı gölgelendirici modellerinin farklı özellikleri vardır. Genel olarak, daha yeni gölgelendirici modelleri genişletilmiş yetenekler sunar, ancak gölgelendirici kodunu çalıştırmak için daha modern grafik donanımı gerektirir. Belirli tür gölgelendiriciler ( **gölgelendirici türü** özelliği tarafından belirtilir) yalnızca daha yeni gölgelendirici modellerinde kullanılabilir — Örneğin, işlem gölgelendiricileri gölgelendirici modeli 5 ' te sunulmuştur.

Bu özellik, HLSL derleyicisine  **\[/t Type] _\[model]** komut satırı bağımsız değişkeninin  **\[model]** bölümüne karşılık gelir. **Gölgelendirici türü** özelliği, bağımsız değişkenin **[Type]** kısmını belirtir.

### <a name="all-resources-bound"></a>Tüm kaynaklar bağlanır

Derleyici, bir gölgelendiricinin başvurabileceğinizden tüm kaynakların bağlandığını ve gölgelendirici yürütme süresi (/all_resources_bound) için iyi durumda olduğunu varsayacaktır. Gölgelendirici modeli 5,1 ve üzeri için kullanılabilir.

### <a name="enable-unbounded-descriptor-tables"></a>Sınırlandırılmamış tanımlayıcı tablolarını etkinleştir

Bir gölgelendiriciye, sınırlandırılmamış aralığa (/enable_unbounded_descriptor_tables) sahip bir kaynak dizisinin bildirimini içerdiğini bildirin. Gölgelendirici modeli 5,1 ve üzeri için kullanılabilir.

### <a name="set-root-signature"></a>Kök Imzasını ayarla

Gölgelendirici bytecode 'a (/setrootsignature) kök imzası iliştirin. Gölgelendirici modeli 5,0 ve üzeri için kullanılabilir.

### <a name="preprocessor-definitions"></a>Önişlemci tanımları

HLSL kaynak kodu dosyasına uygulanacak bir veya daha fazla önişlemci sembol tanımı ekler. Sembol tanımlarını ayırmak için noktalı virgül kullanın.

Bu özellik, HLSL derleyicisinin  **\[/d tanımları]** komut satırı bağımsız değişkenine karşılık gelir.

### <a name="compile-a-direct2d-custom-pixel-shader-effect"></a>Direct2D özel piksel gölgelendirici efekti derle

Piksel gölgelendiricileri içeren bir Direct2D özel efekti derleyin. Köşe veya işlem özel efekti için kullanmayın.

### <a name="multi-processor-compilation"></a>Çok Işlemcili derleme

Aynı anda birden çok örnek çalıştırın.

## <a name="advanced-property-page"></a>Gelişmiş özellik sayfası

### <a name="suppress-startup-banner"></a>Başlangıç başlığını gösterme

Başlangıç başlığının ve bilgi iletisinin görüntülenmesini önler. /nologo

### <a name="treat-warnings-as-errors"></a>Uyarıları hata olarak değerlendir

Tüm derleyici uyarılarını hata olarak değerlendirir. Yeni bir proje için tüm derlemelerde/WX kullanılması en iyi yöntem olabilir; Tüm uyarıların çözümlenmesi, en az olası bulma kod kusurlarını güvence altına alacak.

## <a name="output-files-property-page"></a>Çıkış dosyaları Özellik sayfası

### <a name="header-variable-name"></a>Üst bilgi değişken adı

Üstbilgi dosyasındaki değişken adı için bir ad belirtir (/vn [ad])

### <a name="header-file-name"></a>Üst bilgi dosyası adı

Nesne kodu içeren üstbilgi dosyası için bir ad belirtir. (/FH [ad])

### <a name="object-file-name"></a>Nesne dosyası adı

Nesne dosyası için bir ad belirtir. (/Fo [ad])

### <a name="assembler-output"></a>Derleyici çıkışı

Derleme dili çıkış dosyasının içeriğini belirtir. (/FC,/FX)

**Yapabileceği**

- **Listeleme yok** -liste yok.
- **Yalnızca bütünleştirilmiş kod Listeleme** -derleme kodu dosyası
- **Derleme kodu ve onaltılı** derleme kodu ve onaltılık liste dosyası

### <a name="assembler-output-file"></a>Assembler çıkış dosyası

Derleme kodu liste dosyası için dosya adını belirtir

## <a name="see-also"></a>Ayrıca bkz.

[C++Proje özellik sayfası başvurusu](property-pages-visual-cpp.md)<br>
[Komut Satırı özellik sayfaları](command-line-property-pages.md)<br>
[Gölgelendiriciler derleniyor](https://go.microsoft.com/fwlink/p/?LinkID=258284&clcid=0x409)
