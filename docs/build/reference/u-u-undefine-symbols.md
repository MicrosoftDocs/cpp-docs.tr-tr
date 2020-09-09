---
title: /U, /u (Simge tanımlarını kaldır)
description: Ön işlemci simgelerini kaldırmak için Microsoft C/C++ derleyicisi/U ve/u seçeneklerini kullanın.
ms.date: 09/03/2020
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
ms.openlocfilehash: 78effabba2fa72e5ab7f2dfc6ef91f22383b063f
ms.sourcegitcommit: 0df2b7ab4e81284c5248e4584767591dcc1950c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/09/2020
ms.locfileid: "89609195"
---
# <a name="u-u-undefine-symbols"></a>/U, /u (Simge tanımlarını kaldır)

**`/U`** Derleyici seçeneği, belirtilen Önişlemci sembolünü geri tanımlamıyor. **`/u`** Derleyici seçeneği, derleyicinin tanımladığı Microsoft 'a özgü sembolleri geri tanımlamıyor.

## <a name="syntax"></a>Syntax

> **`/U`**\[ ]*simgesi*\
> **`/u`**

## <a name="arguments"></a>Arguments

* simgesi*<br/>
Tanımlanacak ön işlemci simgesi.

## <a name="remarks"></a>Açıklamalar

**`/U`** Ve seçeneklerinden hiçbiri, **`/u`** yönergesi kullanılarak oluşturulan bir sembolü hiç tanımlamaz **`#define`** .

**`/U`** Seçeneği, daha önce seçeneği kullanılarak tanımlanmış bir sembolü tanımlayabilir **`/D`** .

Varsayılan olarak, derleyici, Microsoft 'a özgü çok sayıda sembol tanımlayabilir. Yaygın olarak kullanılan birkaç tane şunlardır:

| Sembol | İşlev |
|--|--|
| `_CHAR_UNSIGNED` | Varsayılan karakter türü imzasız. [`/J`](j-default-char-type-is-unsigned.md)Seçenek belirtildiğinde tanımlanır. |
| `_CPPRTTI` | Seçeneğiyle derlenen kod için tanımlanır [`/GR`](gr-enable-run-time-type-information.md) . |
| `_CPPUNWIND` | Seçeneğiyle derlenen kod için tanımlanır [`/EHsc`](eh-exception-handling-model.md) . |
| `_DLL` | [`/MD`](md-mt-ld-use-run-time-library.md)Seçenek belirtildiğinde tanımlanır. |
| `_M_IX86` | Varsayılan olarak, x86 hedefleri için 600 olarak tanımlanmıştır. |
| `_MSC_VER` | Her derleyici sürümü için benzersiz bir tamsayı değeri olarak tanımlanır. Daha fazla bilgi için bkz. [önceden tanımlanmış makrolar](../../preprocessor/predefined-macros.md). |
| `_WIN32` | WIN32 uygulamaları için tanımlanır. Her zaman tanımlı. |
| `_MT` | [`/MD`](md-mt-ld-use-run-time-library.md)Veya [`/MT`](md-mt-ld-use-run-time-library.md) seçeneği belirtildiğinde tanımlanır. |

Microsoft 'a özgü önceden tanımlanmış makroların tam listesi için bkz. [önceden tanımlanmış makrolar](../../preprocessor/predefined-macros.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **Gelişmiş** özellik sayfasını seçin.

1. Ön **Işlemci tanımlarını kaldır** veya **Tüm Önişlemci tanımları özelliklerini Kaldır** .

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UndefineAllPreprocessorDefinitions%2A> <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UndefinePreprocessorDefinitions%2A> . veya.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyicisi seçenekleri](compiler-options.md)<br/>
[MSVC derleyicisi komut satırı söz dizimi](compiler-command-line-syntax.md)<br/>
[**`/J`** (Varsayılan karakter türü imzasız)](j-default-char-type-is-unsigned.md)<br/>
[**`/GR`** (Çalışma zamanı türü bilgilerini etkinleştir)](gr-enable-run-time-type-information.md)<br/>
[**`/EH`** (Özel durum işleme modeli)](eh-exception-handling-model.md)<br/>
[**`/MD`**, **`/MT`** , **`/LD`** (Çalışma zamanı kitaplığını kullan)](md-mt-ld-use-run-time-library.md)
