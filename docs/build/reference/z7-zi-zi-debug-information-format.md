---
title: "-Z7, - Zi, - ZI (hata ayıklama bilgileri biçimi) | Microsoft Docs"
ms.custom: 
ms.date: 02/22/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.DebugInformationFormat
- /ZI
- /Zi
- /Z7
- VC.Project.VCCLWCECompilerTool.DebugInformationFormat
dev_langs:
- C++
helpviewer_keywords:
- C7 compatible compiler option [C++]
- Debug Information Format compiler option
- ZI compiler option
- -Zi compiler option [C++]
- /ZI compiler option [C++]
- Z7 compiler option [C++]
- debugging [C++], debug information files
- Zi compiler option [C++]
- /Zi compiler option [C++]
- program database compiler option [C++]
- full symbolic debugging information
- /Z7 compiler option [C++]
- line numbers only compiler option [C++]
- cl.exe compiler, debugging options
- -Z7 compiler option [C++]
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3b55c5ea77b752d4adac8d74abaed245b4d19821
ms.sourcegitcommit: 3038840ca6e4dea01accf733436b99d19ff6c930
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/27/2018
---
# <a name="z7-zi-zi-debug-information-format"></a>/Z7, /Zi, /ZI (Hata Ayıklama Bilgileri Biçimi)

Hata ayıklama bilgisi için oluşturulan programınızı ve bu bilgiler nesne dosyaları veya bir program veritabanı (PDB) dosyasında tutulur türünü belirtir.

## <a name="syntax"></a>Sözdizimi

> **/Z**{**7**|**i**|**I**}  

## <a name="remarks"></a>Açıklamalar

Kod derlenmiş ve hata ayıklama modunda yerleşik olduğunda derleyici işlevleri ve değişkenler, tür bilgilerini ve satır numarası konumları hata ayıklayıcı tarafından kullanılmak için Sembol adları üretir. Bu simgesel hata ayıklama bilgisi derleyici tarafından üretilen nesne dosyaları (.obj dosyaları) veya yürütülebilir dosyası için ayrı bir PDB dosyası (.pdb dosyası) dahil edilebilir.  Hata ayıklama bilgileri biçimi seçeneklerini aşağıdaki bölümlerde açıklanmıştır.  
  
### <a name="none"></a>Yok.

Hiçbir hata ayıklama bilgileri biçimi seçeneği belirtilmezse, varsayılan olarak, derleme daha hızlı olacak şekilde derleyici hiçbir hata ayıklama bilgilerini oluşturur.  
  
### <a name="z7"></a>/Z7

**/Z7** seçeneği kullanmak için tam simgesel hata ayıklama bilgilerini hata ayıklayıcısı ile de içeren nesne dosyaları üretir. Bu nesne dosyaları ve yerleşik yürütülebilir hata ayıklama bilgisi dosyaları önemli ölçüde daha büyük olabilir. Simgesel hata ayıklama bilgilerini adlarını ve türlerini değişkenlerinin yanı sıra işlevleri ve satır numaralarını içerir. PDB dosyası oluşturulur.

İçin dağıtıcıları üçüncü taraf kitaplıkların hata ayıklama sürümleri PDB dosyası olmaması bir avantajı vardır. Ancak, tüm önceden derlenmiş üst bilgileri için nesne dosyaları kitaplığı bağlantı aşamasında ve hata ayıklama için gereklidir. Varsa yalnızca bilgi (kod) .pch nesne dosyasında yazıp, ayrıca kullanmalısınız [/Yl (eklenmeye PCH başvurusu hata ayıklama kitaplığı için)](../../build/reference/yl-inject-pch-reference-for-debug-library.md) kitaplığı derlerken, varsayılan olarak etkinleştirilen seçeneği.

[/GM derlemeyi (etkinleştirmek en az yeniden derleme)](../../build/reference/gm-enable-minimal-rebuild.md) seçeneği kullanılamaz ne zaman **/Z7** belirtilir.

### <a name="zi"></a>/Zi

**/Zı** seçeneği tüm simgesel hata ayıklama bilgileri kullanmak için hata ayıklayıcısı ile içeren ayrı bir PDB dosyası oluşturur. Hata ayıklama bilgilerini nesne dosyalarında dahil edilmeyen veya yürütülebilir dosyası, hangi bunlar çok daha küçük olur.

Kullanımı **/zı** en iyi duruma getirme etkilemez. Ancak, **/zı** anlamına gelmez **/debug**; bkz [/Debug (hata ayıklama bilgisi üret)](../../build/reference/debug-generate-debug-info.md) daha fazla bilgi için.


Belirtirseniz her ikisi de **/zı** ve **/CLR**, <xref:System.Diagnostics.DebuggableAttribute> özniteliği derleme meta verilerde yok yerleştirilir. İsterseniz, kaynak kodunda belirtmeniz gerekir. Bu öznitelik, uygulamanın çalışma zamanı performansını etkileyebilir. Ne hakkında daha fazla bilgi için **Debuggable** özniteliği performansını etkiler ve performans etkisi değiştirebileceğiniz bkz [bir görüntü Debug kolaylaştırma](/dotnet/framework/debug-trace-profile/making-an-image-easier-to-debug).

Derleyici PDB dosya adları *proje*.pdb. Proje dışındaki bir dosyasını derleyin, derleyici VC adlı bir PDB dosyası oluşturur*x*.pdb, burada *x* kullanımda derleyici sürümünün birincil ve ikincil sürüm numarası yapıdır. Derleyici hata ayıklayıcı simgesel ve satır numarası bilgileri konumuna işaret bu seçeneği kullanılarak oluşturulan her nesne dosya adı PDB ve bir tanımlayıcı zaman damgalı imza katıştırır. Ad ve imza PDB dosyasında hata ayıklayıcısı'ndaki yüklenmesi simgeleri çalıştırılabilir dosyanın eşleşmesi gerekir. WinDBG hata ayıklayıcısını kullanarak eşleşmeyen simgeleri yükleyebilirsiniz `.symopt+0x40` komutu. Visual Studio eşleşmeyen simgeleri yüklemek için benzer bir seçeneği yok.

Bir kitaplık kullanılarak derlendi nesnelerden oluşturursanız **/zı**, kitaplık bir programa bağlandığında ilişkili .pdb dosyasını kullanılabilir olması gerekir. Bu nedenle, kitaplık dağıtırsanız, PDB dosyası da dağıtmanız gerekir. PDB dosyaları kullanmadan hata ayıklama bilgilerini içeren bir kitaplığı oluşturmak için seçmelisiniz **/Z7** seçeneği. Önceden derlenmiş üstbilgiler seçenekleri kullanırsanız, hata ayıklama bilgileri önceden derlenmiş üst bilgi ve kaynak kodu geri kalanı için PDB dosyasında yerleştirilir.

### <a name="zi"></a>/ZI

**/Zı** seçeneği benzer **/zi**, ancak destekleyen bir biçimde PDB dosyası üreten [Düzenle ve devam et](/visualstudio/debugger/edit-and-continue-visual-cpp) özelliği. Düzenle ve devam et hata ayıklama özellikleri kullanmak için bu seçeneği kullanmanız gerekir. Düzenle ve devam et özellik Geliştirici üretkenliği için yararlıdır, ancak kod boyutu, performans ve derleyici uyumluluğu sorunlarına neden. Çoğu iyileştirmeler Düzenle ve devam et ile uyumsuz olduğundan kullanarak **/zı** herhangi devre dışı bırakır `#pragma optimize` deyimlerinde kodunuzu. **/Zı** seçeneği, aynı zamanda kullanımı ile uyumlu değil [&#95; &#95; Çizgi &#95; &#95; önceden tanımlanmış makrosu](../../preprocessor/predefined-macros.md); derlenmiş kod **/zı** kullanamazsınız **&#95; &#95; Çizgi &#95; &#95;**  bir tür olmayan şablon bağımsız değişken olarak rağmen **&#95; &#95; Çizgi &#95; &#95;**  makrosu genişletmeleri içinde kullanılabilir.

**/Zı** seçeneği her ikisi de zorlar [/Gy (işlev düzeyi bağlamayı etkinleştir)](../../build/reference/gy-enable-function-level-linking.md) ve [/FC (tam yolu, kaynak kodu dosyasının tanılamadaki)](../../build/reference/fc-full-path-of-source-code-file-in-diagnostics.md) , derlemede kullanılacak seçenekleri.

**/ZI** ile uyumlu olmayan [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).

> [!NOTE]
> **/Zı** seçenek, yalnızca x86 hem x64 işlemciler hedefleme derleyicileri kullanılabilir; Bu derleyici seçeneği ARM işlemcileri hedefleme derleyicileri kullanılabilir değil.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Açık **yapılandırma özellikleri** > **C/C++** > **genel** özellik sayfası.

1. Değiştirme **hata ayıklama bilgileri biçimi** özelliği. Seçin **Tamam** yaptığınız değişiklikleri kaydetmek için.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DebugInformationFormat%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)  
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)  

