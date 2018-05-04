---
title: -Yl (hata ayıklama kitaplığı için PCH Başvurusu Ekle) | Microsoft Docs
ms.custom: ''
ms.date: 01/29/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /yl
dev_langs:
- C++
helpviewer_keywords:
- -Yl compiler option [C++]
- Yl compiler option [C++]
- /Yl compiler option [C++]
ms.assetid: 8e4a396a-6790-4a9f-8387-df015a3220e7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a73e79cd50343292ae63dfa831a7638d6444fc64
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="yl-inject-pch-reference-for-debug-library"></a>/Yl (Hata Ayıklama Kitaplığı için PCH Başvurusu Ekle)

**/Yl** seçeneği önceden derlenmiş üstbilgi dosyasında benzersiz bir simge oluşturur ve bu simgeyi başvuru önceden derlenmiş üst bilgi kullanan tüm nesne dosyaları eklenmiş.

## <a name="syntax"></a>Sözdizimi

>**/Yl**  
>**/Yl**_adı_  
>**/Yl-**  

### <a name="arguments"></a>Arguments

*Adı*  
Benzersiz bir simge bir parçası olarak kullanılan isteğe bağlı adı.

*\-*  
Bir tire (-) açıkça devre dışı bırakır **/Yl** derleyici seçeneği.

## <a name="remarks"></a>Açıklamalar

**/Yl** derleyici seçeneği kullanılarak oluşturulan bir önceden derlenmiş üst bilgi dosyası içinde benzersiz bir simge tanımı oluşturur [/Yc](../../build/reference/yc-create-precompiled-header-file.md) seçeneği. Bu simge başvurularını otomatik olarak kullanarak önceden derlenmiş üst bilgi dahil tüm dosyalardaki eklenen [/Yu](../../build/reference/yu-use-precompiled-header-file.md) derleyici seçeneği. **/Yl** seçeneği varsayılan olarak etkin olduğunda **/Yc** önceden derlenmiş üst bilgi dosyası oluşturmak için kullanılır.

**/Yl**_adı_ seçeneği önceden derlenmiş üst bilgi dosyası tanımlanabilen bir simge oluşturmak için kullanılır. Derleyici kullanan *adı* oluşturur, benzer bağımsız değişken düzenlenmiş simgesi adının bir parçası olarak \_ \_ @@ \_PchSym\_@00@... @ *adı*, burada bir benzersiz derleyici tarafından üretilen ve üç nokta (...) temsil eder dize karakter. Varsa *adı* bağımsız değişken atlanırsa, derleyici sembol adını otomatik olarak oluşturur. Normalde, simgenin adını bilmeniz gerek yoktur. Ancak, projenizin kullandığında birden fazla önceden derlenmiş üst bilgi dosyası **/Yl**_adı_ seçeneği önceden derlenmiş üstbilgi kullanım hangi nesne dosyaları belirlemek yararlı olabilir. Kullanabileceğiniz *adı* bir döküm dosyası simgesi başvuru bulmak için bir arama dizesi olarak.

**/Yl-** varsayılan davranışı devre dışı bırakır ve tanımlayan bir sembol önceden derlenmiş üst bilgi dosyasında eklemez. Bu önceden derlenmiş üst bilgi dahil derlenmiş dosyalar get ortak bir simge başvurusu değil.

Zaman **/Yc** belirtilmezse, tüm **/Yl** seçeneği bu eşleşmelidir herhangi belirttiyseniz, ancak hiçbir etkisi **/Yl** seçeneği geçirilen **/Yc** olduğu Belirtilen.

Kullanırsanız **/Yl-**, **/Yc** ve [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md) önceden derlenmiş üst bilgi dosyası, hata ayıklama bilgileri oluşturma seçenekleri oluşturmak için kullanılan kaynak dosya için nesne dosyasında depolanır önceden derlenmiş üst bilgi yerine ayrı .pdb dosyasını. Bu nesne dosyası sonra bir kitaplık parçası yaptıysanız [LNK1211](../../error-messages/tool-errors/linker-tools-error-lnk1211.md) hataları veya [LNK4206](../../error-messages/tool-errors/linker-tools-warning-lnk4206.md) kaynak dosyasını oluşturmak için kullandıysanız, uyarıları bu kitaplığı ve önceden derlenmiş üstbilgi dosyası kullanma derlemelerde meydana gelebilir önceden derlenmiş üstbilgi dosyası semboller kendisini tanımlamıyor. Nesne dosyasına bir şey kitaplık istemcisinde başvurulduğunda bağlayıcı bağlantısından ilişkili hata ayıklama bilgilerle birlikte nesne dosyası dışarıda bırakılabilir. Bu sorunu çözmek için belirtmek **/Yl** (veya kaldırma **/Yl-** seçeneği) kullandığınızda, **/Yc** önceden derlenmiş üst bilgi dosyasını oluşturmak için. Bu hata ayıklama bilgileri içeren kitaplık nesnesi dosyasından derlemenizde bağlı sağlar.

Önceden derlenmiş üst bilgileri hakkında daha fazla bilgi için bkz:

- [/Y (Önceden Derlenmiş Üst Bilgiler)](../../build/reference/y-precompiled-headers.md)

- [Önceden Derlenmiş Üst Bilgi Dosyaları Oluşturma](../../build/reference/creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Ekleme **/Yl**_adı_ derleyici seçeneği **ek seçenekler** kutusu. Seçin **Tamam** yaptığınız değişiklikleri kaydetmek için.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)  
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)  
