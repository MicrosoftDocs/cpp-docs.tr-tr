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
ms.openlocfilehash: 816ba66c94e616407a8891cd149a41e44e29358d
ms.sourcegitcommit: 6b749db14b4cf3a2b8d581fda6fdd8cb98bc3207
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82825723"
---
# <a name="yl-inject-pch-reference-for-debug-library"></a>/Yl (Hata Ayıklama Kitaplığı için PCH Başvurusu Ekle)

**/Yıl** seçeneği önceden derlenmiş üstbilgi dosyasında benzersiz bir sembol oluşturur ve bu simgeye yönelik bir başvuru, önceden derlenmiş üstbilgiyi kullanan tüm nesne dosyalarına eklenir.

## <a name="syntax"></a>Sözdizimi

>**/Yl**\
>**/Rivl**_adı_\
>**Olduğu için/Yl-**

### <a name="arguments"></a>Bağımsız Değişkenler

*ada*<br/>
Benzersiz simgenin bir parçası olarak kullanılan isteğe bağlı bir ad.

*\-*<br/>
Kısa çizgi (-), **/Rivl** derleyici seçeneğini açıkça devre dışı bırakır.

## <a name="remarks"></a>Açıklamalar

**/Rivl** derleyici seçeneği, [/yıc](yc-create-precompiled-header-file.md) seçeneği kullanılarak oluşturulan önceden derlenmiş üstbilgi dosyasında benzersiz bir sembol tanımı oluşturur. Bu simgeye yapılan başvurular, [/yu](yu-use-precompiled-header-file.md) derleyici seçeneği kullanılarak önceden derlenmiş üstbilgiyi içeren tüm dosyalara otomatik olarak eklenir. **/Rivc** **seçeneği,** önceden derlenmiş bir üstbilgi dosyası oluşturmak için kullanıldığında varsayılan olarak etkindir.

**/Rivname**_name_ seçeneği, önceden derlenmiş üstbilgi dosyasında tanımlanabilir bir sembol oluşturmak için kullanılır. Derleyici, üç nokta *name* (...), bir derleyici tarafından oluşturulan benzersiz bir karakter dizesini `__@@_PchSym_@00@...@name`temsil ettiği gibi, oluşturduğu düzenlenmiş sembol adının bir parçası olarak ad bağımsız değişkenini kullanır. *Ad* bağımsız değişkeni atlanırsa, derleyici otomatik olarak bir sembol adı oluşturur. Normalde, simgenin adını bilmeniz gerekmez. Ancak, projeniz birden fazla önceden derlenmiş üst bilgi dosyası kullandığında, hangi nesne dosyalarının önceden derlenmiş üstbilgiyi kullanacağını belirleyebilmek için **/yıl**_ad_ seçeneği yararlı olabilir. Bir döküm dosyasında sembol başvurusunu bulmak için bir arama dizesi olarak *adı* kullanabilirsiniz.

**/Yıl-** varsayılan davranışı devre dışı bırakır ve önceden derlenmiş üstbilgi dosyasına bir tanımlayıcı sembol yerleştirmez. Bu ön derlenmiş üstbilgiyi içeren derlenmiş dosyalar ortak bir sembol başvurusu almaz.

**/Rivc** belirtilmediğinde, herhangi bir **/i** seçeneğinin etkisi yoktur, ancak belirtilmişse, **/Rivc** belirtildiğinde,/rivl **/Yl** seçeneğiyle eşleşmesi gerekir.

Önceden derlenmiş bir üstbilgi dosyası oluşturmak için **/yıl-**, **/bağımsız** ve [/Z7](z7-zi-zi-debug-information-format.md) seçeneklerini kullanırsanız, hata ayıklama bilgileri ayrı bir. pdb dosyası yerine önceden derlenmiş üstbilgiyi oluşturmak için kullanılan kaynak dosyanın nesne dosyasında depolanır. Bu nesne dosyası daha sonra bir kitaplığın parçası haline getirilirse, önceden derlenmiş üst bilgi dosyasını oluşturmak için kullanılan kaynak dosyası herhangi bir sembolün kendisi tanımlanmıyorsa, bu kitaplığı kullanan yapılarda [LNK1211](../../error-messages/tool-errors/linker-tools-error-lnk1211.md) hataları veya [LNK4206](../../error-messages/tool-errors/linker-tools-warning-lnk4206.md) uyarıları oluşabilir. Bağlayıcı, kitaplık istemcisinde nesne dosyasındaki hiçbir şey başvuruluyorsa, ilişkili hata ayıklama bilgileri ile birlikte nesne dosyasını bağlantıdan dışlayabilir. Bu sorunu çözmek için **/Yıc** ' yi, önceden derlenmiş üst bilgi dosyasını oluşturmak için kullandığınızda **/rivl** (veya **/yıl-** Option seçeneğini kaldırın) belirtin. Bu, hata ayıklama bilgilerini içeren kitaplıktan nesne dosyasının derlemenize bağlı olmasını sağlar.

Önceden derlenmiş üstbilgiler hakkında daha fazla bilgi için bkz.

- [/Y (Önceden Derlenmiş Başlıklar)](y-precompiled-headers.md)

- [Ön derlenmiş üstbilgi dosyaları](../creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **C/C++** > **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** kutusuna **/yıl**_Name_ derleyici seçeneğini ekleyin. Değişikliklerinizi kaydetmek için **Tamam ' ı** seçin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
