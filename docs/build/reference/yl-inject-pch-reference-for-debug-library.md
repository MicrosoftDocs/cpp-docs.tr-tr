---
title: "-Yl (hata ayıklama kitaplığı için PCH Başvurusu Ekle) | Microsoft Docs"
ms.custom: 
ms.date: 12/04/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /yl
dev_langs: C++
helpviewer_keywords:
- -Yl compiler option [C++]
- Yl compiler option [C++]
- /Yl compiler option [C++]
ms.assetid: 8e4a396a-6790-4a9f-8387-df015a3220e7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6e777977f6d869d2bbc28d980f6445851e54396b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="yl-inject-pch-reference-for-debug-library"></a>/Yl (Hata Ayıklama Kitaplığı için PCH Başvurusu Ekle)

**/Yl** seçeneği önceden derlenmiş üst bilgi dosyası için ortak bir simge oluşturur ve bu simgeyi önceden derlenmiş üst bilgi kullanan tüm dosyalarda başvurular yerleştirir. Bu önceden derlenmiş üst bilgi sembolleri için tam türü bilgileri önceden derlenmiş üst bilgi kullanan tüm dosyaları hata ayıklayıcıda için kullanılabilmesini sağlar. Bu seçenek varsayılan olarak etkindir. Bu seçeneğin kullanılması, önceden derlenmiş başlıkları kullanma bağlantılı kitaplıklar hata ayıklama bilgilerini eksik nedeniyle bağlayıcı hataları önleyebilirsiniz.

## <a name="syntax"></a>Sözdizimi

>**/Yl**  
>**/Yl**_adı_  
>**/Yl-**  

### <a name="arguments"></a>Arguments

*adı*  
Bir simge tanımlayın veya önceden derlenmiş üst bilgi kullanan depolanan ve başvurulan nesne dosyaları olarak tanımlamak için kullanılan isteğe bağlı adı.

*\-*  
Bir tire (-) açıkça devre dışı bırakır **/Yl** derleyici seçeneği.

## <a name="remarks"></a>Açıklamalar

**/Yl** önceden derlenmiş üst bilgi içeren her dosyaya önceden derlenmiş üstbilgisinde türleri hakkında tam bilgi almak hata ayıklayıcı seçeneğini etkinleştirir. Bu seçenek bir iç simge adı oluşturur, sembol tanımına göre önceden derlenmiş üst bilgi oluşturmak için kullanılan nesne dosyasına yerleştirir [/Yc](../../build/reference/yc-create-precompiled-header-file.md) seçeneği ve önceden derlenmiş dahil tüm dosyaları sembolü başvuru yerleştirir kullanarak üstbilgi [/Yu](../../build/reference/yu-use-precompiled-header-file.md) derleyici seçeneği. Önceden derlenmiş üst bilgi kullanan tüm kaynak dosyaları adlandırılmış simgenin başvurduğundan bağlayıcı simge ve hata ayıklama bilgileri ilişkili önceden derlenmiş üstbilgi tanımlayan nesne dosyası her zaman bağlar. Bu seçenek varsayılan olarak etkindir.

**/Yl**_adı_ seçeneği açıkça tanımlayıcı simge için önceden derlenmiş üst bilgi dosyasını oluşturmak için kullanılır. Derleyici kullanan *adı* benzer bir simge oluşturmak için bağımsız değişken \_ \_ @@ \_PchSym\_@00@... @*adı* , burada üç nokta (...) temsil bağlayıcı oluşturulan bir karakter dizesi. Bağımsız değişken belirtilmezse, derleyici sembol adını otomatik olarak oluşturur.

**/Yl-** varsayılan davranışı devre dışı bırakır ve tanımlayan bir sembol başvuru önceden derlenmiş üst bilgi içeren nesne dosyaları eklemez. Bu seçenek mevcut önceden derlenmiş üst bilgi dosyası derlenmiş dosyalar için gerekli olabilir.

Kullanırsanız **/Yl-**, **/Yc** ve [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md) derleyici bir kitaplığını oluşturmak için seçenekleri depolanan hata ayıklama bilgilerini içeren bir önceden derlenmiş üst bilgi dosyası oluşturur bir nesne dosyası yerine bir .pdb dosyası. [LNK1211](../../error-messages/tool-errors/linker-tools-error-lnk1211.md) hataları veya [LNK4206](../../error-messages/tool-errors/linker-tools-warning-lnk4206.md) uyarıları, bu kitaplığı kullanan derlemelerde oluşabilir ve kaynak dosyasını önceden derlenmiş üst bilgi oluşturmak için kullanılan önceden derlenmiş üst bilgi semboller tanımlamıyor. Nesne dosyasına bir şey kitaplık istemcisinde başvurulduğunda bağlayıcı bağlantısından ilişkili önceden derlenmiş üstbilgi hata ayıklama bilgileri yanı sıra bu kitaplık nesnesini dosyasını dışarıda bırakılabilir. Sorunu çözmek için belirtmek **/Yl** kullandığınızda **/Yc** önceden derlenmiş üst bilgi dosyası oluşturmak için ve **/Yu** kullanmak için. Bu hata ayıklama bilgilerini içeren nesne dosyası derlemenizde dahil edilmesini sağlar.

Önceden derlenmiş üst bilgileri hakkında daha fazla bilgi için bkz:

- [/Y (önceden derlenmiş başlıklar)](../../build/reference/y-precompiled-headers.md)

- [Önceden Derlenmiş Üst Bilgi Dosyaları Oluşturma](../../build/reference/creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Seçin **komut satırı** özellik sayfasında **C/C++** klasör.

1. Ekleme **/Yl**_adı_ derleyici seçeneği **ek seçenekler** kutusu. Seçin **Tamam** yaptığınız değişiklikleri kaydetmek için.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)  
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)  
