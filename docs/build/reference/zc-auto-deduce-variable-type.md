---
title: /Zc:auto (Değişken Türünü Türet)
ms.date: 02/28/2018
f1_keywords:
- /Zc:auto
helpviewer_keywords:
- -Zc compiler options (C++)
- Deduce variable type (C++)
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 5f5bc102-44c3-4688-bbe1-080594dcee5c
ms.openlocfilehash: 866cccb490136e951effb1f8da20877c8d5ec763
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217187"
---
# <a name="zcauto-deduce-variable-type"></a>`/Zc:auto`(Değişken türünü türet)

**`/Zc:auto`** Derleyici seçeneği derleyiciye değişkenleri bildirmek için [ `auto` anahtar sözcüğünü](../../cpp/auto-keyword.md) nasıl kullanacağınızı söyler. Varsayılan seçeneğini belirtirseniz, **`/Zc:auto`** derleyici, belirtilen değişkenin türünü başlatma ifadesinden çıkarır. Belirtirseniz **`/Zc:auto-`** , derleyici değişkeni otomatik depolama sınıfına ayırır.

## <a name="syntax"></a>Sözdizimi

> **`/Zc:auto`**[**`-`**]

## <a name="remarks"></a>Açıklamalar

C++ standardı, anahtar sözcüğü için özgün ve düzeltilmiş anlamı tanımlar **`auto`** . Visual Studio 2010 ' den önce, anahtar sözcüğü otomatik depolama sınıfında bir değişken bildirir; diğer bir deyişle, yerel ömrü olan bir değişkendir. Visual Studio 2010 ' den itibaren anahtar sözcüğü, bildirimin başlatma ifadesinden bir değişkenin türünü çıkarır. **`/Zc:auto`** Derleyiciye anahtar sözcüğünün düzeltilmiş anlamını kullanmasını söylemek için derleyici seçeneğini kullanın **`auto`** . **`/Zc:auto`** Seçeneği varsayılan olarak açık olur. [`/permissive-`](permissive-standards-conformance.md)Seçeneği varsayılan ayarını değiştirmez **`/Zc:auto`** .

**`auto`** Anahtar sözcüğü kullanımınız geçerli derleyici seçeneği ile çelişkili ise derleyici uygun bir tanılama iletisi yayınlar **`/Zc:auto`** . Daha fazla bilgi için bkz. [ `auto` anahtar sözcük](../../cpp/auto-keyword.md). Visual C++ uygunluk sorunları hakkında daha fazla bilgi için bkz. [Standart olmayan davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Visual Studio 'da Bu derleyici seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. **`/Zc:auto`** **`/Zc:auto-`** **Ek seçenekler:** bölmesine ekleyin.

## <a name="see-also"></a>Ayrıca bkz.

[`/Zc`Uyumsuzlu](zc-conformance.md)<br/>
[`auto`Sözcükle](../../cpp/auto-keyword.md)
