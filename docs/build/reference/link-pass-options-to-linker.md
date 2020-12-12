---
description: :/Link hakkında daha fazla bilgi edinin (bağlayıcı seçeneklerini bağlayıcıya geçirin)
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
ms.openlocfilehash: 3617a005e6adbc41a589606aa145712fa2df442d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199499"
---
# <a name="link-pass-options-to-linker"></a>/link (Seçenekleri Bağlayıcıya Geçir)

Bağlayıcıya bir veya daha fazla bağlayıcı seçeneği geçirir.

## <a name="syntax"></a>Syntax

> **/Link** *bağlayıcı-seçenekler*

## <a name="arguments"></a>Arguments

*bağlayıcı-seçenekler*<br/>
Bağlayıcıya geçirilecek bağlayıcı seçeneği veya seçenekleri.

## <a name="remarks"></a>Açıklamalar

**/Link** seçeneği ve bağlayıcı seçenekleri herhangi bir dosya adı ve CL seçeneğinden sonra gelmelidir. **/Link** ve bağlayıcı seçenekleri arasında bir boşluk gereklidir. Daha fazla bilgi için bkz. [MSVC bağlayıcı başvurusu](linking.md).

## <a name="example"></a>Örnek

Bu örnek komut satırı *Hello. cpp* ' i derler ve var olan nesne dosyası *. obj* öğesine bağlar. Daha sonra bağlayıcıya ek bir **/Version** komutu geçirir:

`cl /W4 /EHsc hello.cpp there.obj /link /VERSION:3.14`

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

IDE, kodunuzu derlemek ve bağlamak için normalde ayrı komutlar gönderir. Proje özellik sayfalarınızda bağlayıcı seçeneklerini belirleyebilirsiniz.

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **bağlayıcı** klasörünü seçin.

1. Bir veya daha fazla özelliği değiştirin. Değişikliklerinizi kaydetmek için **Tamam ' ı** seçin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bu derleyici seçeneği program aracılığıyla değiştirilemez.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
