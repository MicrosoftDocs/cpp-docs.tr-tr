---
title: /volatile (volatile Anahtar Sözcük Yorumu)
ms.date: 11/04/2016
f1_keywords:
- /volatile:iso
- /volatile:ms
- /volatile
helpviewer_keywords:
- /volatile compiler option
- /volatile compiler option [C++]
- -volatile compiler option
- volatile compiler option [C++]
- volatile compiler option
- -volatile compiler option [C++]
ms.assetid: 9d08fcc6-5bda-44c8-8151-8d8d54f164b8
ms.openlocfilehash: 7c2c1cd477b424f56e66bd9246e7bde76ad06120
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223791"
---
# <a name="volatile-volatile-keyword-interpretation"></a>/volatile (volatile Anahtar Sözcük Yorumu)

[Geçici](../../cpp/volatile-cpp.md) anahtar sözcüğünün nasıl yorumlanacağını belirtir.

## <a name="syntax"></a>Sözdizimi

> **/volatile:**{**ISO** | **MS**}

## <a name="arguments"></a>Arguments

**/volatile: ISO**<br/>
**`volatile`** ISO standardı C++ dili tarafından tanımlanan katı semantiğini seçer. Alma/bırakma semantiği geçici erişimlerde garanti edilmez. Derleyici ARM hedefliyorsa, bu varsayılan yorumdur **`volatile`** .

**/volatile: MS**<br/>
Microsoft genişletilmiş **`volatile`** semantiğini seçer, bu da bellek sıralaması ekleme, ISO standardı C++ dilinin ötesine garanti sağlar. Alma/bırakma semantiği geçici erişimlerde garanti edilir. Ancak, bu seçenek, derleyicinin ARM ve diğer zayıf bellek sıralama mimarilerinde önemli ek yük ekleyebilecek donanım belleği engelleri oluşturma işlemini de zorlar. Derleyici ARM haricinde herhangi bir platformu hedefliyorsa, bu varsayılan yorumdur **`volatile`** .

## <a name="remarks"></a>Açıklamalar

İş parçacıkları arasında paylaşılan bellekle ilgilenirken açık eşitleme temelleri ve derleyici iç bilgileri ile birlikte **/volatile: iso** kullanmanızı önemle tavsiye ederiz. Daha fazla bilgi için bkz. [geçici](../../cpp/volatile-cpp.md).

Bir projenin ortasında var olan kodun bağlantı noktası varsa veya bu seçeneği değiştirirseniz, semantik farkından etkilenen kod konumlarını belirlemek için Uyarı [C4746](../../error-messages/compiler-warnings/compiler-warning-c4746.md) etkinleştirilmesi yararlı olabilir.

`#pragma`Bu seçeneği denetlemek için eşdeğer bir değer yoktur.

### <a name="to-set-the-volatile-compiler-option-in-visual-studio"></a>Visual Studio 'da/volatile derleyici seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** kutusunda, **/volatile: ISO** veya **/volatile: MS** ekleyin ve ardından değişikliklerinizi kaydetmek için **Tamam** ' ı veya **Uygula** ' yı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[volatile](../../cpp/volatile-cpp.md)<br/>
[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
