---
title: /Zs (Yalnızca Sözdizimi Denetimi)
ms.date: 11/04/2016
f1_keywords:
- /zs
helpviewer_keywords:
- -Zs compiler option [C++]
- Syntax Check Only compiler option
- Zs compiler option
- /Zs compiler option [C++]
ms.assetid: b4b41e6a-3f41-4d09-9cb6-fde5aa2cfecf
ms.openlocfilehash: e3713312b71c4cd539d40e09a3eaa821a2e5caed
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315423"
---
# <a name="zs-syntax-check-only"></a>/Zs (Yalnızca Sözdizimi Denetimi)

Yalnızca komut satırında kaynak dosyalarının söz dizimini kontrol etmek için derleyiciye bildirir.

## <a name="syntax"></a>Sözdizimi

```
/Zs
```

## <a name="remarks"></a>Açıklamalar

Bu seçeneği kullandığınızda hiçbir çıkış dosyası oluşturulur ve hata iletileri, Standart çıkışa yazılır.

**/Zs** seçeneğini bulun ve derleme ve bir kaynak dosyası bağlamak için önce söz dizimi hataları düzeltmek için hızlı bir yol sağlar.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Derleyici seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
