---
title: /Yl (Hata Ayıklama Kitaplığı için PCH Başvurusu Ekle)
ms.date: 01/29/2018
f1_keywords:
- /yl
helpviewer_keywords:
- -Yl compiler option [C++]
- Yl compiler option [C++]
- /Yl compiler option [C++]
ms.assetid: 8e4a396a-6790-4a9f-8387-df015a3220e7
ms.openlocfilehash: 92e47836e0fdae077defa0fe35b515ab4ca20a66
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316255"
---
# <a name="yl-inject-pch-reference-for-debug-library"></a>/Yl (Hata Ayıklama Kitaplığı için PCH Başvurusu Ekle)

**/Yl** seçeneği önceden derlenmiş üst bilgi dosyasında benzersiz bir simge oluşturur ve bu sembole bir başvuru önceden derlenmiş üst bilgi kullanan tüm nesne dosyalarında eklenmiş olur.

## <a name="syntax"></a>Sözdizimi

>**/Yl**
> **/Yl**_adı_
> **/Yl-**

### <a name="arguments"></a>Arguments

*Adı*<br/>
Benzersiz bir simge bir parçası olarak kullanılan isteğe bağlı adı.

*\-*<br/>
Bir tire (-) açıkça devre dışı bırakır **/Yl** derleyici seçeneği.

## <a name="remarks"></a>Açıklamalar

**/Yl** derleyici seçeneği kullanılarak oluşturulan bir ön derlenmiş üstbilgi dosyası içinde benzersiz bir simge tanımı oluşturur [/Yc](yc-create-precompiled-header-file.md) seçeneği. Bu sembol başvuruları oluşturdukça otomatik önceden derlenmiş üst bilgi kullanarak dahil tüm dosyalarında [/Yu](yu-use-precompiled-header-file.md) derleyici seçeneği. **/Yl** seçeneği varsayılan olarak etkin olduğunda **/Yc** Ön derlenmiş üstbilgi dosyası oluşturmak için kullanılır.

**/Yl**_adı_ seçeneği önceden derlenmiş üst bilgi dosyasında tanımlanabilir bir simge oluşturmak için kullanılır. Derleyicinin kullandığı *adı* oluşturur, benzer bağımsız değişken olarak düzenlenmiş sembol adının bir kısmını `__@@_PchSym_@00@...@name`, burada dize benzersiz bir derleyici tarafından oluşturulan üç nokta (...) temsil karakter. Varsa *adı* bağımsız değişken atlanırsa, derleyici bir sembol adı otomatik olarak oluşturur. Normalde, sembol adını bilmeniz gerekmez. Ancak, projenizi kullandığında birden fazla önceden derlenmiş üst bilgi dosyası **/Yl**_adı_ seçeneği ön derlenmiş üstbilgi kullanımı hangi nesne dosyaları belirlemek yararlı olabilir. Kullanabileceğiniz *adı* sembol başvurusu bir döküm dosyası içinde bulunacak bir arama dizesi olarak.

**/Yl-** varsayılan davranışı devre dışı bırakır ve tanımlayıcı bir sembol önceden derlenmiş üst bilgi dosyasında eklemez. Bu önceden derlenmiş üst bilgi içeren derlenmiş dosyalar, ortak bir sembol başvurusu elde ederim.

Zaman **/Yc** belirtilmezse, tüm **/Yl** seçeneği, eşleşmelidir herhangi belirttiyseniz, ancak hiçbir etkisi **/Yl** seçeneği geçirilen **/Yc** olduğu Belirtilen.

Kullanırsanız **/Yl-**, **/Yc** ve [/z7](z7-zi-zi-debug-information-format.md) seçenekleri, hata ayıklama bilgileri bir ön derlenmiş üstbilgi dosyası oluşturmak için nesne dosyası oluşturmak için kullanılan kaynak dosyası için depolanır önceden derlenmiş üst bilgi yerine ayrı bir .pdb dosyası. Bu nesne dosyası bir kitaplık parçası sonra denenirse [LNK1211](../../error-messages/tool-errors/linker-tools-error-lnk1211.md) hataları veya [LNK4206](../../error-messages/tool-errors/linker-tools-warning-lnk4206.md) uyarıları kaynak dosyası oluşturmak için kullanılıyorsa bu kitaplığı ve Ön derlenmiş üstbilgi dosyası kullanan derlemeler meydana gelebilir önceden derlenmiş üstbilgi dosyasının kendisini simgeleri tanımlamıyor. Hiçbir nesne dosyası kitaplığı istemcisinde başvurulduğunda bağlantıdan ilişkili hata ayıklama bilgilerinin yanı sıra bağlayıcı nesne dosya dışarıda bırakılabilir. Bu sorunu çözmek için belirtin **/Yl** (veya kaldırma **/Yl-** seçeneği) kullandığınızda, **/Yc** önceden derlenmiş üstbilgi dosyası oluşturmak için. Bu nesne dosyası hata ayıklama bilgilerini içeren kitaplıktan yapınızda bağlı sağlar.

Önceden derlenmiş üst bilgiler hakkında daha fazla bilgi için bkz:

- [/Y (Önceden Derlenmiş Üst Bilgiler)](y-precompiled-headers.md)

- [Önceden Derlenmiş Üst Bilgi Dosyaları](../creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Ekleme **/Yl**_adı_ derleyici seçeneğini **ek seçenekler** kutusu. Seçin **Tamam** yaptığınız değişiklikleri kaydedin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
