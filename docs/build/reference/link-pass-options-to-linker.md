---
title: /link (Seçenekleri Bağlayıcıya Geçir)
ms.date: 03/25/2019
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
ms.openlocfilehash: 37743e855c933b6236b5e7a837db257f332a3037
ms.sourcegitcommit: bbaf65f8ed1af12828b38f8eacd24f934ac0e538
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/17/2019
ms.locfileid: "67155785"
---
# <a name="link-pass-options-to-linker"></a>/link (Seçenekleri Bağlayıcıya Geçir)

Bir veya daha fazla bağlayıcı seçenekleri bağlayıcıya iletir.

## <a name="syntax"></a>Sözdizimi

> **/ link** *bağlayıcı seçenekleri*

## <a name="arguments"></a>Arguments

*bağlayıcı seçenekleri*<br/>
Seçenekleri bağlayıcıya geçirilemez ve bağlayıcı seçeneği.

## <a name="remarks"></a>Açıklamalar

**/Link** seçeneği ve bağlayıcı seçenekleri herhangi bir dosya adlarını ve CL seçenekleri sonra görünmelidir. Bir arasında gerekli bir alandır **/link** ve bağlayıcı seçenekleri. Daha fazla bilgi için [MSVC bağlayıcı başvurusu](linking.md).

## <a name="example"></a>Örnek

Bu örnek komut satırı derleme *hello.cpp* ve varolan nesne dosyasına bağlantılar *there.obj*. Daha sonra ek bir geçirir **/VERSION** bağlayıcı komutu:

`cl /W4 /EHsc hello.cpp there.obj /link /VERSION:3.14`

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

IDE, normalde derlemek ve kodunuzu bağlamak için ayrı komutlar gönderir. Bağlayıcı seçenekleri, proje özelliği sayfalarından ayarlayabilirsiniz.

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** klasör.

1. Bir veya daha fazla özelliklerini değiştirin. Seçin **Tamam** yaptığınız değişiklikleri kaydedin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bu derleyici seçeneğini program aracılığıyla değiştirilemez.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
