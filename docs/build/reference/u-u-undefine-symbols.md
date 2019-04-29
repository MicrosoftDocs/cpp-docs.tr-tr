---
title: /U, /u (Simge Tanımlarını Kaldır)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.UndefinePreprocessorDefinitions
- VC.Project.VCCLWCECompilerTool.UndefinePreprocessorDefinitions
- VC.Project.VCCLCompilerTool.UndefineAllPreprocessorDefinitions
- /u
- VC.Project.VCCLWCECompilerTool.UndefineAllPreprocessorDefinitions
helpviewer_keywords:
- -U compiler option [C++]
- Undefine Symbols compiler option
- /U compiler option [C++]
- U compiler option [C++]
ms.assetid: 7bc0474f-6d1f-419b-807d-0d8816763b2a
ms.openlocfilehash: bfc03ebd5c900bf8bf81b4a50eed02111baf85ee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62317009"
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
|_CHAR_UNSIGNED|Varsayılan karakter türü imzalanmamış. Tanımlanır [/J](j-default-char-type-is-unsigned.md) seçeneği belirtildi.|
|_CPPRTTI|İle derlenen kod için tanımlanan [GR](gr-enable-run-time-type-information.md) seçeneği.|
|_CPPUNWIND|İle derlenen kod için tanımlanan [/ehsc](eh-exception-handling-model.md) seçeneği.|
|_DLL|Tanımlanır [/MD](md-mt-ld-use-run-time-library.md) seçeneği belirtildi.|
|_M_IX86|600 x86 için tanımlanan varsayılan hedefler.|
|_MSC_VER|Daha fazla bilgi için [önceden tanımlanmış makrolar](../../preprocessor/predefined-macros.md).|
|_WIN32|WIN32 uygulamaları için tanımlanır. Her zaman tanımlı.|
|_MT|Tanımlanır [/MD veya/MT](md-mt-ld-use-run-time-library.md) seçeneği belirtildi.|

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **Gelişmiş** özellik sayfası.

1. Değiştirme **önişlemci tanımlarını Kaldır** veya **tüm önişlemci tanımlarını Kaldır** özellikleri.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UndefineAllPreprocessorDefinitions%2A> veya <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UndefinePreprocessorDefinitions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
[/J (Varsayılan Karakter Türü İmzasız)](j-default-char-type-is-unsigned.md)<br/>
[/GR (Çalışma Zamanı Türü Bilgileri Etkinleştir)](gr-enable-run-time-type-information.md)<br/>
[/EH (Özel Durum İşleme Modeli)](eh-exception-handling-model.md)<br/>
[/MD, /MT, /LD (Çalışma Zamanı Kitaplığını Kullan)](md-mt-ld-use-run-time-library.md)
