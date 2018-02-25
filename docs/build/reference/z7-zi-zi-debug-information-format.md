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
ms.openlocfilehash: f6e3de89c5336cda98960b67b80932df8f67d183
ms.sourcegitcommit: 2cca90d965f76ebf1d741ab901693a15d5b8a4df
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/24/2018
---
# <a name="z7-zi-zi-debug-information-format"></a>/Z7, /Zi, /ZI (Hata Ayıklama Bilgileri Biçimi)

Hata ayıklama bilgisi için oluşturulan programınızı ve bu bilgiler nesne dosyaları veya bir program veritabanı (PDB) dosyasında tutulur türünü belirtir.

## <a name="syntax"></a>Sözdizimi

> **/Z**{**7**|**i**|**I**}  

## <a name="remarks"></a>Açıklamalar

Hata ayıklama bilgileri biçimi seçeneklerini aşağıdaki bölümlerde açıklanmıştır.  
  
### <a name="none"></a>Yok.

Hiçbir hata ayıklama bilgileri biçimi seçeneği belirtilmezse, varsayılan olarak, derleme daha hızlı olacak şekilde derleyici hiçbir hata ayıklama bilgilerini oluşturur.  
  
### <a name="z7"></a>/Z7

**/Z7** seçeneği oluşturan bir *nesne dosyası*, kullanım için hata ayıklayıcısı ile tam simgesel hata ayıklama bilgilerini içeren bir .obj uzantısına sahip bir dosya. Simgesel hata ayıklama bilgilerini adlarını ve türlerini değişkenlerinin yanı sıra işlevleri ve satır numaralarını içerir. Hayır *PDB dosyası*, .pdb uzantılı bir dosya oluşturulur.

İçin dağıtıcıları üçüncü taraf kitaplıkların PDB dosyası olmaması bir avantajı vardır. Ancak, nesne için önceden derlenmiş üst bilgiler bağlantı aşamasında ve hata ayıklama için gerekli dosyalar. Varsa yalnızca bilgi (kod) .pch nesne dosyalarında yazıp, ayrıca kullanmalısınız [/Yl (eklenmeye PCH başvurusu hata ayıklama kitaplığı için)](../../build/reference/yl-inject-pch-reference-for-debug-library.md) seçeneği varsayılan olarak etkindir.

### <a name="zi"></a>/Zi

**/Zı** seçenek türü bilgilerini ve hata ayıklayıcısı ile kullanım simgesel hata ayıklama bilgilerini içeren bir PDB dosyası oluşturur. Simgesel hata ayıklama bilgilerini adlarını ve türlerini değişkenlerinin yanı sıra işlevleri ve satır numaralarını içerir.

Kullanımı **/zı** en iyi duruma getirme etkilemez. Ancak, **/zı** anlamına gelmez **/debug**; bkz [/Debug (hata ayıklama bilgisi üret)](../../build/reference/debug-generate-debug-info.md) daha fazla bilgi için.

Zaman **/zı** belirtilirse, tür bilgilerini PDB dosyasında ve nesne dosyasındaki yerleştirilir.

Kullanabileceğiniz [/GM derlemeyi (etkinleştirmek en az yeniden derleme)](../../build/reference/gm-enable-minimal-rebuild.md) ile birlikte **/zı**, ancak **/GM derlemeyi** ne zaman kullanılabilir değil **/Z7** belirtilir.

Belirtirseniz her ikisi de **/zı** ve **/CLR**, <xref:System.Diagnostics.DebuggableAttribute> özniteliği derleme meta verilerde yok yerleştirilir. İsterseniz, kaynak kodunda belirtmeniz gerekir. Bu öznitelik, uygulamanın çalışma zamanı performansını etkileyebilir. Ne hakkında daha fazla bilgi için **Debuggable** özniteliği performansını etkiler ve performans etkisi değiştirebileceğiniz bkz [bir görüntü Debug kolaylaştırma](/dotnet/framework/debug-trace-profile/making-an-image-easier-to-debug).

### <a name="zi"></a>/ZI

**/Zı** seçeneği üreten PDB dosyası destekleyen bir biçimde [Düzenle ve devam et](/visualstudio/debugger/edit-and-continue-visual-cpp) özelliği. Düzenle ve devam et hata ayıklaması kullanmak istiyorsanız, bu seçeneği kullanmanız gerekir. Düzenle ve devam et özellik Geliştirici üretkenliği için yararlıdır, ancak derleyici uyumluluğu, kod boyutu ve performans sorunlarına neden. Çoğu iyileştirmeler Düzenle ve devam et ile uyumsuz olduğundan kullanarak **/zı** herhangi devre dışı bırakır `#pragma optimize` deyimlerinde kodunuzu. **/Zı** seçeneği, aynı zamanda kullanımı ile uyumlu değil [&#95; &#95; Çizgi &#95; &#95; önceden tanımlanmış makrosu](../../preprocessor/predefined-macros.md). Derlenmiş kod **/zı** kullanamazsınız **&#95; &#95; Çizgi &#95; &#95;**  bir tür olmayan şablon bağımsız değişken olarak rağmen **&#95; &#95; Çizgi &#95; &#95;**  makrosu genişletmeleri içinde kullanılabilir.

**/Zı** seçeneği her ikisi de zorlar [/Gy (işlev düzeyi bağlamayı etkinleştir)](../../build/reference/gy-enable-function-level-linking.md) ve [/FC (tam yolu, kaynak kodu dosyasının tanılamadaki)](../../build/reference/fc-full-path-of-source-code-file-in-diagnostics.md) , derlemede kullanılacak seçenekleri.

**/ZI** ile uyumlu olmayan [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).

> [!NOTE]
> **/Zı** seçenek, yalnızca x86 hem x64 işlemciler hedefleme derleyicileri kullanılabilir; Bu derleyici seçeneği ARM işlemcileri hedefleme derleyicileri kullanılabilir değil.

Derleyici PDB dosya adları *proje*.pdb. Proje dışındaki bir dosyasını derleyin, derleyici VC adlı bir PDB dosyası oluşturur*x*0.pdb, burada *x* ana sürüm numarası kullanımda Visual Studio sürümü. Hata ayıklayıcı simgesel ve satır numarası bilgileri konumuna işaret eden, bu seçenek kullanılarak oluşturulan her .obj dosyasında PDB adını derleyici katıştırır. Bu seçeneği kullandığınızda, hata ayıklama bilgileri .pdb dosyasını yerine .obj dosyaları depolandığından, .obj dosyaları daha küçük.

Bu seçenek kullanılarak derlendi nesnelerinden bir kitaplık oluşturursanız, kitaplık bir programa bağlandığında ilişkili .pdb dosyasını kullanılabilir olması gerekir. Bu nedenle, kitaplık dağıtırsanız, PDB dağıtmanız gerekir.

.Pdb dosyaları kullanmadan hata ayıklama bilgilerini içeren bir kitaplığı oluşturmak için derleyicinin C 7.0 uyumlu seçin (**/Z7**) seçeneği. Önceden derlenmiş üstbilgiler seçenekleri kullanırsanız, hata ayıklama bilgileri önceden derlenmiş üst bilgi ve kaynak kodu geri kalanı için PDB dosyasında yerleştirilir. **/Yd** seçeneği Program veritabanı seçeneği belirtildiğinde yoksayılır.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Açık **yapılandırma özellikleri** > **C/C++** > **genel** özellik sayfası.

1. Değiştirme **hata ayıklama bilgileri biçimi** özelliği. Seçin **Tamam** yaptığınız değişiklikleri kaydetmek için.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DebugInformationFormat%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)  
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)  

