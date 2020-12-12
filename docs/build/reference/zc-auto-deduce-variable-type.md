---
description: 'Hakkında daha fazla bilgi edinin: `/Zc:auto` (değişken türünü türet)'
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
ms.openlocfilehash: d20f377fc653e9c3cceb5c3e81b5e5e8a815bcad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114721"
---
# <a name="zcauto-deduce-variable-type"></a>`/Zc:auto` (Değişken türünü türet)

**`/Zc:auto`** Derleyici seçeneği derleyiciye değişkenleri bildirmek için [ `auto` anahtar sözcüğünü](../../cpp/auto-cpp.md) nasıl kullanacağınızı söyler. Varsayılan seçeneğini belirtirseniz, **`/Zc:auto`** derleyici, belirtilen değişkenin türünü başlatma ifadesinden çıkarır. Belirtirseniz **`/Zc:auto-`** , derleyici değişkeni otomatik depolama sınıfına ayırır.

## <a name="syntax"></a>Syntax

> **`/Zc:auto`**[**`-`**]

## <a name="remarks"></a>Açıklamalar

C++ standardı, anahtar sözcüğü için özgün ve düzeltilmiş anlamı tanımlar **`auto`** . Visual Studio 2010 ' den önce, anahtar sözcüğü otomatik depolama sınıfında bir değişken bildirir; diğer bir deyişle, yerel ömrü olan bir değişkendir. Visual Studio 2010 ' den itibaren anahtar sözcüğü, bildirimin başlatma ifadesinden bir değişkenin türünü çıkarır. **`/Zc:auto`** Derleyiciye anahtar sözcüğünün düzeltilmiş anlamını kullanmasını söylemek için derleyici seçeneğini kullanın **`auto`** . **`/Zc:auto`** Seçeneği varsayılan olarak açık olur. [`/permissive-`](permissive-standards-conformance.md)Seçeneği varsayılan ayarını değiştirmez **`/Zc:auto`** .

**`auto`** Anahtar sözcüğü kullanımınız geçerli derleyici seçeneği ile çelişkili ise derleyici uygun bir tanılama iletisi yayınlar **`/Zc:auto`** . Daha fazla bilgi için bkz. [ `auto` anahtar sözcük](../../cpp/auto-cpp.md). Visual C++ uygunluk sorunları hakkında daha fazla bilgi için bkz. [Standart olmayan davranış](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Visual Studio 'da Bu derleyici seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. **`/Zc:auto`** **`/Zc:auto-`** **Ek seçenekler:** bölmesine ekleyin.

## <a name="see-also"></a>Ayrıca bkz.

[`/Zc` Uyumsuzlu](zc-conformance.md)<br/>
[`auto` Sözcükle](../../cpp/auto-cpp.md)
