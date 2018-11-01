---
title: /link (Seçenekleri Bağlayıcıya Geçir)
ms.date: 11/04/2016
f1_keywords:
- /link
helpviewer_keywords:
- /link compiler option [C++]
- pass options to linker
- link compiler option [C++]
- linker [C++], passing options to
- -link compiler option [C++]
- cl.exe compiler [C++], passing options to linker
ms.assetid: 16902a94-c094-4328-841f-3ac94ca04848
ms.openlocfilehash: dfa39988782a0c5bd121b6e18402d3f6b67a13e9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50574934"
---
# <a name="link-pass-options-to-linker"></a>/link (Seçenekleri Bağlayıcıya Geçir)

Bir veya daha fazla bağlayıcı seçenekleri bağlayıcıya iletir.

## <a name="syntax"></a>Sözdizimi

```
/link linkeroptions
```

## <a name="arguments"></a>Arguments

*linkeroptions*<br/>
Seçenekleri bağlayıcıya geçirilemez ve bağlayıcı seçeneği.

## <a name="remarks"></a>Açıklamalar

**/Link** seçeneği ve bağlayıcı seçenekleri herhangi bir dosya adlarını ve CL seçenekleri sonra görünmelidir. Bir arasında gerekli bir alandır **/link** ve `linkeroptions`. Daha fazla bilgi için [bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Bağlayıcı özellik sayfasını tıklatın.

1. Bir veya daha fazla özelliklerini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bu derleyici seçeneğini program aracılığıyla değiştirilemez.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)