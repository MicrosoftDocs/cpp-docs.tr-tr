---
title: /FP (adı &period;pch dosyası)
description: /Fp derleyici seçeneği önceden derlenmiş üst bilgi dosyası adını belirtmek için kullanın.
ms.date: 05/31/2019
f1_keywords:
- VC.Project.VCCLCompilerTool.PrecompiledHeaderFile
- /fp
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
ms.openlocfilehash: 6e7faa934d14acb5d129173c5e0c7ee67d6caf2b
ms.sourcegitcommit: 540fa2f5015de1adfa7b6bf823f6eb4ed5a6a4bd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/03/2019
ms.locfileid: "66460881"
---
# <a name="fp-name-periodpch-file"></a>/FP (adı &period;pch dosyası)

Bir yol adı için varsayılan yolu adını kullanmak yerine önceden derlenmiş üst bilgi sağlar.

## <a name="syntax"></a>Sözdizimi

> **/ FP**<em>yol adı</em>

## <a name="remarks"></a>Açıklamalar

Kullanım **/FP** seçeneğini [/Yc (önceden derlenmiş üst bilgi dosyası oluştur)](yc-create-precompiled-header-file.md) veya [/Yu (önceden derlenmiş üst bilgi dosyasını kullanma)](yu-use-precompiled-header-file.md) önceden derlenmiş üst bilgi (PCH) yolu ve dosya adını belirtmek için dosya. Varsayılan olarak, **/Yc** seçeneği PCH dosya adı kaynak dosyanın temel adı kullanarak oluşturur ve bir *pch* uzantısı.

Bir parçası olarak bir uzantı belirtmezseniz *pathname*, uzantısı *pch* varsayılır. Bir eğik çizgi kullanarak bir dizin adı belirttiğinizde ( **/** ) sonunda *pathname*, vc varsayılan dosya adıdır*sürüm*0.pch, burada  *Sürüm* ana Visual Studio araç seti sürümüdür. Bu dizin mevcut olmalıdır veya C1083 hatası oluşturulur.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Açık **yapılandırma özellikleri** > **C /C++**  > **önceden derlenmiş üst bilgiler** özellik sayfası.

1. Değiştirme **önceden derlenmiş üst bilgi çıkış dosyası** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="examples"></a>Örnekler

Programınızın hata ayıklama derlemesi için önceden derlenmiş üst bilgi dosyasının sürümü adlı ayrı bir oluşturmak için bir komutu gibi belirtebilirsiniz:

```CMD
CL /DDEBUG /Zi /Yc /FpDPROG.PCH PROG.CPP
```

Aşağıdaki komut MYPCH.pch adlı bir ön derlenmiş üstbilgi dosyasının kullanımını belirtir. Derleyici, sonuna kadar MYAPP.h PROG.cpp kaynak kodunda işlemini gerçekleştirir ve önceden derlenmiş kod içinde MYPCH.pch koyar. MYPCH.pch içeriğini kullanır ve kalan PROG.cpp bir .obj dosyası oluşturmak için derler. Bu örnek çıktısı PROG.exe adlı bir dosyadır.

```CMD
CL /YuMYAPP.H /FpMYPCH.PCH PROG.CPP
```

## <a name="see-also"></a>Ayrıca bkz.

[Çıktı Dosyası (/F) Seçenekleri](output-file-f-options.md)<br/>
[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
[Yol Adını Belirtme](specifying-the-pathname.md)
