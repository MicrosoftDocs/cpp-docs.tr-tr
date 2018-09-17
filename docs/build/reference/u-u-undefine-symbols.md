---
title: -U, -u (simge tanımlarını Kaldır) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.UndefinePreprocessorDefinitions
- VC.Project.VCCLWCECompilerTool.UndefinePreprocessorDefinitions
- VC.Project.VCCLCompilerTool.UndefineAllPreprocessorDefinitions
- /u
- VC.Project.VCCLWCECompilerTool.UndefineAllPreprocessorDefinitions
dev_langs:
- C++
helpviewer_keywords:
- -U compiler option [C++]
- Undefine Symbols compiler option
- /U compiler option [C++]
- U compiler option [C++]
ms.assetid: 7bc0474f-6d1f-419b-807d-0d8816763b2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 34030a8ef91e5a25bdb1a13981925c5ddf1f05df
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45721558"
---
# <a name="u-u-undefine-symbols"></a>/U, /u (Simge Tanımlarını Kaldır)

**/U** derleyici seçeneği tanımsızı belirtilen önişlemci sembolü. **/U** derleyici seçeneği tanımsızı derleyici tanımlayan Microsoft'a özgü simgeler.

## <a name="syntax"></a>Sözdizimi

```
/U[ ]symbol
/u
```

## <a name="arguments"></a>Arguments

*Sembol*<br/>
Tanımsız önişlemci sembolü.

## <a name="remarks"></a>Açıklamalar

Ne **/U** veya **/u** seçeneği kullanılarak oluşturulmuş bir simge tanımlarını Kaldır **#define** yönergesi.

**/U** seçeneği kullanılarak önceden tanımlanmış bir simge tanımlarını Kaldır **/D** seçeneği.

Varsayılan olarak, derleyici aşağıdaki Microsoft'a özgü simgeleri tanımlar.

|Sembol|İşlev|
|------------|--------------|
|_CHAR_UNSIGNED|Varsayılan karakter türü imzalanmamış. Tanımlanır [/J](../../build/reference/j-default-char-type-is-unsigned.md) seçeneği belirtildi.|
|_CPPRTTI|İle derlenen kod için tanımlanan [GR](../../build/reference/gr-enable-run-time-type-information.md) seçeneği.|
|_CPPUNWIND|İle derlenen kod için tanımlanan [/ehsc](../../build/reference/eh-exception-handling-model.md) seçeneği.|
|_DLL|Tanımlanır [/MD](../../build/reference/md-mt-ld-use-run-time-library.md) seçeneği belirtildi.|
|_M_IX86|600 x86 için tanımlanan varsayılan hedefler.|
|_MSC_VER|Daha fazla bilgi için [önceden tanımlanmış makrolar](../../preprocessor/predefined-macros.md).|
|_WIN32|WIN32 uygulamaları için tanımlanır. Her zaman tanımlı.|
|_MT|Tanımlanır [/MD veya/MT](../../build/reference/md-mt-ld-use-run-time-library.md) seçeneği belirtildi.|

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **Gelişmiş** özellik sayfası.

1. Değiştirme **önişlemci tanımlarını Kaldır** veya **tüm önişlemci tanımlarını Kaldır** özellikleri.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UndefineAllPreprocessorDefinitions%2A> veya <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UndefinePreprocessorDefinitions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
[/J (varsayılan karakter türü imzasız)](../../build/reference/j-default-char-type-is-unsigned.md)
[/GR (çalışma zamanı türü bilgileri etkinleştir)](../../build/reference/gr-enable-run-time-type-information.md)
[/EH (özel durum işleme modeli)](../../build/reference/eh-exception-handling-model.md) 
 [/MD, / MT, /LD (çalışma zamanı kitaplığını kullan)](../../build/reference/md-mt-ld-use-run-time-library.md)