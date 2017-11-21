---
title: "-Z7, - Zi, - ZI (hata ayıklama bilgileri biçimi) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.DebugInformationFormat
- /zi
- /z7
- VC.Project.VCCLWCECompilerTool.DebugInformationFormat
dev_langs: C++
helpviewer_keywords:
- C7 compatible compiler option [C++]
- -Zl compiler option [C++]
- Debug Information Format compiler option
- ZI compiler option
- -Zi compiler option [C++]
- /ZI compiler option [C++]
- Z7 compiler option [C++]
- debugging [C++], debug information files
- Zi compiler option [C++]
- none compiler option [C++]
- /Zi compiler option [C++]
- program database compiler option [C++]
- full symbolic debugging information
- /Z7 compiler option [C++]
- line numbers only compiler option [C++]
- cl.exe compiler, debugging options
- -Z7 compiler option [C++]
ms.assetid: ce9fa7e1-0c9b-47e3-98ea-26d1a16257c8
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 782420e674d6101f49e2b361c888a8f4b0b4c1ec
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="z7-zi-zi-debug-information-format"></a>/Z7, /Zi, /ZI (Hata Ayıklama Bilgileri Biçimi)
Hata ayıklama bilgisi için oluşturulan programınızı ve bu bilgiler nesne (.obj) dosyalarında veya program veritabanı (PDB) tutulur türünü seçin.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Z{7|i|I}  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Seçenekler aşağıdaki tabloda açıklanmıştır.  
  
 Yok.  
 Derleme daha hızlı olması için hiçbir hata ayıklama bilgilerini oluşturur.  
  
 **/ Z7**  
 Hata ayıklayıcı kullanmak için tam simgesel hata ayıklama bilgileri içeren bir .obj dosyası oluşturur. Simgesel hata ayıklama bilgilerini adlarını ve türlerini değişkenlerinin yanı sıra işlevleri ve satır numaralarını içerir. .Pdb dosyası oluşturulur.  
  
 İçin dağıtıcıları üçüncü taraf kitaplıkların .pdb dosyasını olmaması bir avantajı vardır. Ancak, önceden derlenmiş üstbilgiler .obj dosyaları gerekli bağlantı aşamasında ve hata ayıklama. Varsa yalnızca bilgi (kod) .pch nesne dosyalarında yazıp, da ile derlemek sahip olursunuz [/Yl (eklenmeye PCH başvurusu hata ayıklama kitaplığı için)](../../build/reference/yl-inject-pch-reference-for-debug-library.md).  
  
 **/Zi**  
 Tür bilgileri ve hata ayıklayıcısı ile kullanım simgesel hata ayıklama bilgileri içeren bir program veritabanı (PDB) oluşturur. Simgesel hata ayıklama bilgilerini adlarını ve türlerini değişkenlerinin yanı sıra işlevleri ve satır numaralarını içerir.  
  
 **/Zi** en iyi duruma getirme etkilemez. Ancak, **/zı** anlamına gelmez **/debug**; bkz [/Debug (hata ayıklama bilgisi üret)](../../build/reference/debug-generate-debug-info.md) daha fazla bilgi için.  
  
 Tür bilgileri .pdb dosyasını ve .obj dosyasında yerleştirilir.  
  
 Kullanabileceğiniz [/GM derlemeyi (etkinleştirmek en az yeniden derleme)](../../build/reference/gm-enable-minimal-rebuild.md) ile **/zı**, ancak **/GM derlemeyi** ile derleme yapılırken kullanılamıyor **/Z7**.  
  
 İle derleme yapılırken **/zı** ve **/CLR**, <xref:System.Diagnostics.DebuggableAttribute> özniteliği değil derleme meta verilerde yerleştirilir; istiyorsanız kaynak kodunda belirtmeniz gerekir. Bu öznitelik, uygulamanın çalışma zamanı performansını etkileyebilir. Debuggable özniteliği performansı nasıl etkiler ve performans etkisi nasıl değiştirileceği hakkında daha fazla bilgi için bkz: [bir görüntü Debug kolaylaştırma](/dotnet/framework/debug-trace-profile/making-an-image-easier-to-debug).  
  
 **/ZI**  
 Düzenle ve devam et özelliğini destekleyen bir biçimde, yukarıda açıklandığı gibi bir program veritabanı oluşturur. Düzenle ve devam et hata ayıklaması kullanmak istiyorsanız, bu seçeneği kullanmanız gerekir. Çoğu iyileştirmeler Düzenle ve devam et ile uyumsuz olduğundan kullanarak **/zı** herhangi devre dışı bırakır `#pragma optimize` deyimlerinde kodunuzu.  
  
 **/ZI** neden [/Gy (işlev düzeyi bağlamayı etkinleştir)](../../build/reference/gy-enable-function-level-linking.md) ve [/FC (tam yolu, kaynak kodu dosyasının tanılamadaki)](../../build/reference/fc-full-path-of-source-code-file-in-diagnostics.md) , derlemede kullanılacak.  
  
 **/ZI** ile uyumlu olmayan [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
> [!NOTE]
>  **/ZI** yalnızca kullanılabilir x86 hem x64 işlemciler; hedefleme derleyicileri Bu derleyici seçeneği ARM işlemcileri hedefleme derleyicileri kullanılabilir değil.  
  
 Program veritabanı derleyici adları *proje*.pdb. Bir dosyayı bir proje olmadan derleme yaparsanız derleyici VC adlı bir veritabanı oluşturur*x*0.pdb. burada *x* ana sürümü [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] kullanımda. Hata ayıklayıcı simgesel ve satır numarası bilgileri konumuna işaret eden, bu seçenek kullanılarak oluşturulan her .obj dosyasında PDB adını derleyici katıştırır. Bu seçeneği kullandığınızda, hata ayıklama bilgileri .pdb dosyasını yerine .obj dosyaları depolandığından, .obj dosyaları daha küçük olacaktır.  
  
 Bu seçenek kullanılarak derlendi nesnelerinden bir kitaplık oluşturursanız, kitaplık bir programa bağlandığında ilişkili .pdb dosyasını kullanılabilir olması gerekir. Bu nedenle, kitaplık dağıtırsanız, PDB dağıtmanız gerekir.  
  
 .Pdb dosyaları kullanmadan hata ayıklama bilgilerini içeren bir kitaplığı oluşturmak için derleyicinin C 7.0 uyumlu seçin (**/Z7**) seçeneği. Önceden derlenmiş üstbilgiler seçenekleri kullanırsanız, hata ayıklama bilgileri önceden derlenmiş üst bilgi ve kaynak kodu geri kalanı için PDB yerleştirilir. **/Yd** seçeneği Program veritabanı seçeneği belirtildiğinde yoksayılır.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **genel** özellik sayfası.  
  
4.  Değiştirme **hata ayıklama bilgileri biçimi** özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DebugInformationFormat%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)