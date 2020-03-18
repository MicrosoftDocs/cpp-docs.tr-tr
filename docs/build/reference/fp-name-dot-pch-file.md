---
title: /FP (&period;pch dosyasını Adlandır)
description: Ön derlenmiş üstbilgi dosyası adını belirtmek için/FP derleyici seçeneğini kullanın.
ms.date: 05/31/2019
f1_keywords:
- VC.Project.VCCLCompilerTool.PrecompiledHeaderFile
- VC.Project.VCCLWCECompilerTool.PrecompiledHeaderFile
helpviewer_keywords:
- Fp compiler option [C++]
- -Fp compiler option [C++]
- naming precompiler header files
- PCH files, naming
- names [C++], PCH
- .pch files, naming
- precompiled header files, naming
- /Fp compiler option [C++]
ms.assetid: 0fcd9cbd-e09f-44d3-9715-b41efb5d0be2
ms.openlocfilehash: d62c5bd9fc7920c0a2a5530879680fad2a01d39a
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439788"
---
# <a name="fp-name-periodpch-file"></a>/FP (&period;pch dosyasını Adlandır)

Varsayılan yol adını kullanmak yerine önceden derlenmiş üst bilgi için bir yol adı sağlar.

## <a name="syntax"></a>Sözdizimi

> **/FP**<em>yol adı</em>

## <a name="remarks"></a>Açıklamalar

Ön derlenmiş üstbilgi (PCH) dosyasının yolunu ve dosya adını belirtmek için [/N (önceden derlenmiş başlık dosyası oluştur)](yc-create-precompiled-header-file.md) veya [/yu (önceden derlenmiş üst bilgi dosyasını kullan)](yu-use-precompiled-header-file.md) ile **/FP** seçeneğini kullanın. Varsayılan olarak, **/Yıc** seçeneği kaynak dosyanın temel adını ve bir *PCH* uzantısını kullanarak bir PCH dosya adı oluşturur.

*Yol adının*bir parçası olarak bir uzantı belirtmezseniz, bir *PCH* uzantısı varsayılır. *Yol*adının sonunda bir eğik çizgi ( **/** ) kullanarak bir dizin adı belirttiğinizde, varsayılan dosya adı VC*sürümü*0. pch olur; burada *Sürüm* , Visual Studio araç takımının ana sürümüdür. Bu dizin var olmalıdır veya hata C1083 oluşturulmuştur.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **C/C++**  > **önceden derlenmiş üstbilgiler** özellik sayfasını açın.

1. **Ön derlenmiş üstbilgi çıkış dosyası** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="examples"></a>Örnekler

Programınızın hata ayıklama derlemesi için önceden derlenmiş üstbilgi dosyasının ayrı adlandırılmış bir sürümünü oluşturmak için, şöyle bir komut belirtebilirsiniz:

```CMD
CL /DDEBUG /Zi /Yc /FpDPROG.PCH PROG.CPP
```

Aşağıdaki komut, MYPCH. pch adlı önceden derlenmiş bir üstbilgi dosyasının kullanımını belirtir. Derleyici, program. cpp içindeki kaynak kodu MYAPP. h sonu ile önceden derler ve önceden derlenmiş kodu MYPCH. pch dosyasına koyar. Daha sonra MYPCH. pch içeriğini kullanır ve bir. obj dosyası oluşturmak için program. cpp geri kalanını derler. Bu örneğin çıktısı, PROG. exe adlı bir dosyadır.

```CMD
CL /YuMYAPP.H /FpMYPCH.PCH PROG.CPP
```

## <a name="see-also"></a>Ayrıca bkz.

[Çıktı Dosyası (/F) Seçenekleri](output-file-f-options.md)<br/>
[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
[Yol Adını Belirtme](specifying-the-pathname.md)
