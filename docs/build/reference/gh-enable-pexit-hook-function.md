---
title: /GH (_pexit kanca işlevini etkinleştir)
description: Yerel bir _pexit Kanca işlevi ayarlamak için/GH derleyici seçeneğini açıklar.
ms.date: 07/06/2020
f1_keywords:
- _pexit
helpviewer_keywords:
- /Gh compiler option [C++]
- Gh compiler option [C++]
- _pexit function
- -Gh compiler option [C++]
ms.assetid: 93181453-2676-42e5-bf63-3b19e07299b6
ms.openlocfilehash: b8fc355503055af8b928874ced39cb8224901d3e
ms.sourcegitcommit: 85d96eeb1ce41d9e1dea947f65ded672e146238b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/07/2020
ms.locfileid: "86058613"
---
# <a name="gh-enable-_pexit-hook-function"></a>/GH (_pexit kanca işlevini etkinleştir)

`_pexit`Her yöntemin veya işlevin sonundaki işlevi çağırır.

## <a name="syntax"></a>Sözdizimi

> **`/GH`**

## <a name="remarks"></a>Açıklamalar

`_pexit`İşlev herhangi bir kitaplığın parçası değil. İçin bir tanım sağlamanız gerekir `_pexit` .

Açıkça çağırmanız planlanmadığınız takdirde `_pexit` , prototip sağlamanız gerekmez. İşlev, girişte tüm Yazmaçların içeriğini itmeli ve çıkışta değiştirilmeyen içeriği bir pencerede döndürmelidir. Aşağıdaki prototiple sahip gibi görünmelidir:

```cpp
void __declspec(naked) __cdecl _pexit( void );
```

Bu bildirim 64-bit projeler için kullanılamaz.

`_pexit`Şuna benzerdir `_penter` ; bir işlevin nasıl yazılacağını gösteren bir örnek için bkz. [ `/Gh` (_penter Kanca işlevini etkinleştir)](gh-enable-penter-hook-function.md) `_penter` .

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** özellik sayfasını açın.

1. **Ek seçenekler** kutusunda derleyici seçeneğini girin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyicisi seçenekleri](compiler-options.md)<br/>
[MSVC derleyicisi komut satırı söz dizimi](compiler-command-line-syntax.md)<br/>
[`/Gh`(_Penter Kanca işlevini etkinleştir)](gh-enable-penter-hook-function.md)
