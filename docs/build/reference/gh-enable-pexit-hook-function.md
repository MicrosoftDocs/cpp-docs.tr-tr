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
ms.openlocfilehash: 5382ba90f490aaa12e9e55767fdf15170a69ced5
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749231"
---
# <a name="gh-enable-_pexit-hook-function"></a>/GH (_pexit Kanca İşlevini Etkinleştir)

Her `_pexit` yöntemin veya işlevin sonundaki işlevi çağırır.

## <a name="syntax"></a>Sözdizimi

```
/GH
```

## <a name="remarks"></a>Açıklamalar

İşlev `_pexit` herhangi bir kitaplığın bir parçası değildir ve `_pexit`bir tanım sağlamak size kalmış.

Açıkça aramayı `_pexit`planlamadığınız sürece, bir prototip sağlamanız gerekmez. İşlev aşağıdaki prototipe sahipmiş gibi görünmelidir ve girişteki tüm kayıtların içeriğini itmeli ve çıkışta değişmemiş içeriği patlatmalıdır:

```cpp
void __declspec(naked) __cdecl _pexit( void );
```

`_pexit`benzer; `_penter` bir `_pexit` işlevin nasıl yazılalabildiğini görmek için [/Gh (Enable _penter Hook Function)](gh-enable-penter-hook-function.md) bölümüne bakın.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik Sayfaları** iletişim kutusunu açın. Ayrıntılar için [Visual Studio'da C++ derleyicisi ayarlanın ve özellikler oluşturun.](../working-with-project-properties.md)

1. **C/C++** klasörünü tıklatın.

1. Komut **Satırı** özelliği sayfasını tıklatın.

1. **Ek Seçenekler** kutusuna derleyici seçeneğini yazın.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
