---
title: -Fp (adı. PCH dosyası) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.PrecompiledHeaderFile
- /fp
- VC.Project.VCCLWCECompilerTool.PrecompiledHeaderFile
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0a851f93ae845d56b9c986e822e94970ad5cccd5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427140"
---
# <a name="fp-name-pch-file"></a>/Fp (.Pch Dosyası Adlandır)

Bir yol adı için varsayılan yolu adını kullanmak yerine önceden derlenmiş üst bilgi sağlar.

## <a name="syntax"></a>Sözdizimi

> **/ FP**<em>yol adı</em>

## <a name="remarks"></a>Açıklamalar

Bu seçeneği kullanın [/Yc (önceden derlenmiş üst bilgi dosyası oluştur)](../../build/reference/yc-create-precompiled-header-file.md) veya [/Yu (önceden derlenmiş üst bilgi dosyasını kullanma)](../../build/reference/yu-use-precompiled-header-file.md) bir yol adı için varsayılan yolu adını kullanmak yerine önceden derlenmiş üst bilgi sağlamak için. Ayrıca **/FP** ile **/Yc** farklıdır bir ön derlenmiş üstbilgi dosyası kullanımını belirlemek için **/Yc**<em>filename</em> bağımsız değişken ve Kaynak dosyanın temel adından.

Yol adının bir parçası olarak bir uzantı belirtmezseniz .pch uzantısı varsayılır. Dizin olmadan bir dosya adı belirtirseniz, VC varsayılan dosya adı olan*x*0.pch, burada *x* önemli Visual C++ sürümü kullanılıyor.

Ayrıca **/FP** seçeneğini **/Yu**.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **önceden derlenmiş üst bilgiler** özellik sayfası.

1. Değiştirme **önceden derlenmiş üst bilgi dosyası** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderFile%2A>.

## <a name="example"></a>Örnek

Programınızın hata ayıklama sürümü için bir ön derlenmiş üstbilgi dosyası oluşturmak istediğiniz ve üst bilgi dosyaları hem de kaynak kodu derleme yapıyorsanız, bir komut gibi belirtebilirsiniz:

```
CL /DDEBUG /Zi /Yc /FpDPROG.PCH PROG.CPP
```

## <a name="example"></a>Örnek

Aşağıdaki komut MYPCH.pch adlı bir ön derlenmiş üstbilgi dosyasının kullanımını belirtir. Derleyici, PROG.cpp kaynak kodunda MYAPP.h ile derlenmiş ve önceden derlenmiş kod MYPCH.pch içinde bulunduğu varsayılır. MYPCH.pch içeriğini kullanır ve kalan PROG.cpp bir .obj dosyası oluşturmak için derler. Bu örnek çıktısı PROG.exe adlı bir dosyadır.

```
CL /YuMYAPP.H /FpMYPCH.PCH PROG.CPP
```

## <a name="see-also"></a>Ayrıca Bkz.

[Çıktı Dosyası (/F) Seçenekleri](../../build/reference/output-file-f-options.md)<br/>
[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
[Yol Adını Belirtme](../../build/reference/specifying-the-pathname.md)