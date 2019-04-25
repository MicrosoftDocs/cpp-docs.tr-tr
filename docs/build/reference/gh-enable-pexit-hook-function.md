---
title: /GH (_pexit Kanca İşlevini Etkinleştir)
ms.date: 11/04/2016
f1_keywords:
- _pexit
helpviewer_keywords:
- /Gh compiler option [C++]
- Gh compiler option [C++]
- _pexit function
- -Gh compiler option [C++]
ms.assetid: 93181453-2676-42e5-bf63-3b19e07299b6
ms.openlocfilehash: 077096cc296f2aa2128127493a84a91da9a067c5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62270919"
---
# <a name="gh-enable-pexit-hook-function"></a>/GH (_pexit Kanca İşlevini Etkinleştir)

Çağrıları `_pexit` sonunda her bir yöntem veya işlev, işlev.

## <a name="syntax"></a>Sözdizimi

```
/GH
```

## <a name="remarks"></a>Açıklamalar

`_pexit` İşlevi herhangi kitaplığının parçası değildir ve sizin için bir tanım sağlamak için en fazla `_pexit`.

Açıkça çağırmak planlamıyorsanız `_pexit`, bir prototip sağlamanız gerekmez. İşlev aşağıdaki prototipe sahip, içeriği tüm kayıtları girişinde anında iletme gerekir ve Çıkışta değişmeden içerik pop gibi görünmelidir:

```
void __declspec(naked) __cdecl _pexit( void );
```

`_pexit` benzer `_penter`; bkz [/Gh (_penter kanca işlevini etkinleştir)](gh-enable-penter-hook-function.md) nasıl yazılacağını gösteren bir örnek bir `_pexit` işlevi.

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
