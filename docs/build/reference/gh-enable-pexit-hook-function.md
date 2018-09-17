---
title: -GH (_pexit kanca işlevini etkinleştir) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _pexit
dev_langs:
- C++
helpviewer_keywords:
- /Gh compiler option [C++]
- Gh compiler option [C++]
- _pexit function
- -Gh compiler option [C++]
ms.assetid: 93181453-2676-42e5-bf63-3b19e07299b6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 489ff00571c79d89c9e807f0d8796989e7a0f84f
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714994"
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
void __declspec(naked) _cdecl _pexit( void );
```

`_pexit` benzer `_penter`; bkz [/Gh (_penter kanca işlevini etkinleştir)](../../build/reference/gh-enable-penter-hook-function.md) nasıl yazılacağını gösteren bir örnek bir `_pexit` işlevi.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Derleyici seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)