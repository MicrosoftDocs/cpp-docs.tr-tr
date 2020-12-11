---
description: 'Hakkında daha fazla bilgi edinin: `/Zc:externConstexpr` (extern constexpr değişkenlerini etkinleştir)'
title: /Zc:externConstexpr (extern constexpr değişkenlerini etkinleştir)
ms.date: 02/28/2018
f1_keywords:
- /Zc:externConstexpr
helpviewer_keywords:
- -Zc:externConstexpr compiler option (C++)
- extern constexpr variables (C++)
ms.assetid: 4da5e33a-2e4d-4ed2-8616-bd8f43265c27
ms.openlocfilehash: 5f3120ba467c70cde2d0deb6932e408a2cd688c8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97156131"
---
# <a name="zcexternconstexpr-enable-extern-constexpr-variables"></a>`/Zc:externConstexpr` (Extern constexpr değişkenlerini etkinleştir)

**`/Zc:externConstexpr`** Derleyici seçeneği derleyicinin C++ standardına uymasını ve değişkenler için dış bağlantıya izin vermesini söyler **`constexpr`** . Varsayılan olarak, **`constexpr`** anahtar sözcüğünü belirtseniz bile Visual Studio her zaman bir iç bağlantı sağlar **`extern`** .

## <a name="syntax"></a>Syntax

> **`/Zc:externConstexpr`**[**`-`**]

## <a name="remarks"></a>Açıklamalar

**`/Zc:externConstexpr`** Derleyici seçeneği, derleyicinin kullanılarak belirtilen değişkenlere dış bağlantı uygulamasını sağlar `extern constexpr` . Visual Studio 'nun önceki sürümlerinde ve varsayılan olarak veya **`/Zc:externConstexpr-`** belirtilmişse, **`constexpr`** **`extern`** anahtar sözcüğü kullanılsa bile, Visual Studio değişkenlere iç bağlantı uygular. Bu **`/Zc:externConstexpr`** seçenek, Visual Studio 2017 güncelleştirme 15,6 ' den başlayarak kullanılabilir. ve varsayılan olarak kapalıdır. [`/permissive-`](permissive-standards-conformance.md)Seçenek etkin değil **`/Zc:externConstexpr`** .

Bir üst bilgi dosyası, tanımlanmış bir değişken içeriyorsa `extern constexpr` , [`__declspec(selectany)`](../../cpp/selectany.md) yinelenen bildirimleri bağlantılı ikilide tek bir örnekle birleştirmek için işaretlenmelidir. Aksi takdirde, tek tanım kuralı ihlalleri için LNK2005 gibi bağlayıcı hataları görebilirsiniz.

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Visual Studio 'da Bu derleyici seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. **`/Zc:externConstexpr`** **`/Zc:externConstexpr-`** **Ek seçenekler:** bölmesine ekleyin.

## <a name="see-also"></a>Ayrıca bkz.

[`/Zc` Uyumsuzlu](zc-conformance.md)<br/>
[`auto` Sözcükle](../../cpp/auto-cpp.md)
