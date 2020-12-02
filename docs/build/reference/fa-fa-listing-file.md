---
title: /FA, /Fa (Listeleme dosyası)
description: Microsoft C++/FA ve/FA (listeleme dosyası) derleyici seçeneği için başvuru kılavuzu.
ms.date: 11/21/2020
f1_keywords:
- VC.Project.VCCLWCECompilerTool.AssemblerListingLocation
- VC.Project.VCCLCompilerTool.ConfigureASMListing
- VC.Project.VCCLWCECompilerTool.AssemblerOutput
- VC.Project.VCCLCompilerTool.AssemblerListingLocation
- /fa
- VC.Project.VCCLCompilerTool.AssemblerOutput
- VC.Project.VCCLCompilerTool.UseUnicodeForAssemblerListing
helpviewer_keywords:
- FA compiler option [C++]
- /FA compiler option [C++]
- -FA compiler option [C++]
- listing file type
- assembly-only listing
ms.openlocfilehash: 7e8e39fea55bb69eaa0ae914eeabcafef4ac7849
ms.sourcegitcommit: 432c24dde31c400437c4320e8432b1ddb232f844
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96440235"
---
# <a name="fa-fa-listing-file"></a>`/FA`, `/Fa` (Listeleme dosyası)

Assembler kodu içeren bir listeleme dosyası oluşturur.

## <a name="syntax"></a>Syntax

> **`/FA`**[**`c`**\][**`s`**\][**`u`**]\
> **`/Fa`**_PathName_

## <a name="remarks"></a>Açıklamalar

**`/FA`** Derleyici seçeneği, derleme içindeki her bir çeviri birimi için genellikle bir C veya C++ kaynak dosyasına karşılık gelen bir assembler listeleme dosyası oluşturur. Varsayılan olarak, yalnızca Assembler, ANSI olarak kodlanmış liste dosyasına dahil edilmiştir. **`c`** **`s`** **`u`** **`/FA`** Makine kodunun veya kaynak kodun, assembler listesi ile birlikte çıkışı YAPıLıP yapılmayacağını ve listenin UTF-8 olarak kodlanıp kodlanmadığını denetlemek için isteğe bağlı, ve bağımsız değişkenler.

Varsayılan olarak, her listeleme dosyası kaynak dosyayla aynı temel adı alır ve bir *`.asm`* uzantıya sahiptir. Makine kodu, seçeneği kullanılarak dahil edildiğinde **`c`** , liste dosyası bir *`.cod`* uzantıya sahiptir. Liste dosyasının adını ve uzantısını ve seçeneğini kullanarak oluşturulduğu dizini değiştirebilirsiniz **`/Fa`** .

### <a name="fa-arguments"></a>`/FA` değişkenlerinden

seçim
Listeye yalnızca assembler dili dahil edilir.

**`c`**\
İsteğe bağlı. , Listede makine kodunu içerir.

**`s`**\
İsteğe bağlı. Listede kaynak kodu içerir.

**`u`**\
İsteğe bağlı. Liste dosyasını UTF-8 biçiminde kodlar ve bir bayt sırası işaretleyicisi içerir. Varsayılan olarak, dosya ANSI olarak kodlanır. **`u`** Herhangi bir sistemde doğru şekilde görüntülenen bir liste dosyası oluşturmak için veya bir Unicode kaynak kodu dosyalarını derleyiciye girdi olarak kullanıyorsanız kullanın.

**`s`** Ve **`u`** belirtilirse ve bir kaynak kod dosyası UTF-8 dışında bir Unicode kodlaması kullanıyorsa, dosyadaki kod satırları *`.asm`* doğru görüntülenmeyebilir.

### <a name="fa-argument"></a>`/Fa` bağımsız değişkeni

seçim
Derlemedeki her kaynak kodu dosyası için bir *kaynak. asm* dosyası oluşturulur.

*kısaltın*\
Derleyici, geçerli dizine *filename*. asm adlı bir liste dosyası koyar. Bu bağımsız değişken formu yalnızca tek bir kaynak kod dosyası derlenirken geçerlidir.

*filename. Extension*\
Derleyici, geçerli dizine *filename. Extension* adlı bir listeleme dosyası koyar. Bu bağımsız değişken formu yalnızca tek bir kaynak kod dosyası derlenirken geçerlidir.

*dizinden*__\\__\
Derleyici, derlemedeki her kaynak kodu dosyası için bir *source_file. asm* dosyası oluşturur. Belirtilen *dizine* yerleştirilir. Sondaki ters eğik çizgi gereklidir. Yalnızca geçerli diskteki yollara izin veriliyor.

*Dizin* __\\__ *dosya adı*\
*Filename. asm* adlı bir liste dosyası belirtilen *dizine* yerleştirilir. Bu bağımsız değişken formu yalnızca tek bir kaynak kod dosyası derlenirken geçerlidir.

*Dizin* __\\__ *filename. Extension*\
*Dosya adı. uzantısı* adlı bir listeleme dosyası belirtilen *dizine* yerleştirildi. Bu bağımsız değişken formu yalnızca tek bir kaynak kod dosyası derlenirken geçerlidir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **çıkış dosyaları** özellik sayfasını seçin.

1. Assembler, makine ve kaynak kodu için **/fac** ve **/Fas** seçeneklerini ayarlamak üzere **assembler çıkış** özelliğini değiştirin. ANSI veya UTF-8 çıkışı seçeneğini ayarlamak için, **assembler Için Unicode listeleme** özelliğini değiştirin **`/FAu`** . Dosya adı ve konumu listeleme seçeneğini ayarlamak için **ASM liste konumunu** değiştirin **`/Fa`** .

Her iki **derleyici çıkışını** ayarlama ve **assembler listesi özellikleri için Unicode kullanma** , [komut satırı uyarısı D9025](../../error-messages/tool-errors/command-line-warning-d9025.md)neden olabilir. IDE 'de bu seçenekleri birleştirmek için, bunun yerine **komut satırı** özellik sayfasındaki **ek seçenekler** alanını kullanın.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AssemblerListingLocation%2A> <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AssemblerOutput%2A> . veya. **/FAU** belirtmek için bkz <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> ..

## <a name="example"></a>Örnek

Aşağıdaki komut satırı adlı Birleşik kaynak ve makine kodu listesini üretir *`HELLO.cod`* :

```cmd
CL /FAcs HELLO.CPP
```

## <a name="see-also"></a>Ayrıca bkz.

[Çıktı dosyası (/F) seçenekleri](output-file-f-options.md)\
[MSVC derleyici seçenekleri](compiler-options.md)\
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)\
[Yol adını belirtme](specifying-the-pathname.md)
