---
title: '/ ZC: externconstexpr (extern constexpr değişkenlerini etkinleştir) | Microsoft Docs'
ms.custom: ''
ms.date: 02/28/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Zc:externConstexpr
dev_langs:
- C++
helpviewer_keywords:
- -Zc:externConstexpr compiler option (C++)
- extern constexpr variables (C++)
ms.assetid: 4da5e33a-2e4d-4ed2-8616-bd8f43265c27
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 34aea466a3e673c3eebb3b415d544d9299fed615
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713148"
---
# <a name="zcexternconstexpr-enable-extern-constexpr-variables"></a>/ ZC: externconstexpr (extern constexpr değişkenlerini etkinleştir)

**/ZC: externconstexpr** derleyici seçeneği C++ standardına uygun ve dış bağlantısı için izin vermek için derleyiciye `constexpr` değişkenleri. Varsayılan olarak, Visual Studio her zaman sunan bir `constexpr` değişken iç bağlantı, belirttiğiniz olsa bile `extern` anahtar sözcüğü.

## <a name="syntax"></a>Sözdizimi

> **/Zc:externConstexpr**[**-**]

## <a name="remarks"></a>Açıklamalar

**/ZC: externconstexpr** derleyici seçeneği, harici bağlantı kullanılarak bildirilen değişkenler uygulamak derleyicinin neden `extern constexpr`. Varsayılan olarak ve Visual Studio'nun önceki sürümlerinde veya **/Zc:externConstexpr-** belirtilirse, Visual Studio iç bağlantı için geçerli `constexpr` değişkenleri bile `extern` anahtar sözcüğü kullanılır. **/ZC: externconstexpr** Visual Studio 2017 güncelleştirme 15.6 sürümünde başlangıç seçeneği kullanılabilir. ve varsayılan olarak kapalıdır. [/ Permissive-](permissive-standards-conformance.md) seçeneği sağlamaz **/ZC: externconstexpr**.

Bir üstbilgi dosyası bildirilen bir değişken içeriyorsa `extern constexpr`, işaretlenmesi gerekir [__declspec(selectany)](../../cpp/selectany.md) bağlı ikili dosyada tek bir örnek yinelenen bildirimlerini birleştirmek için. Aksi takdirde bağlayıcı hatalarını, örneğin, tek tanım kuralı ihlallerini için LNK2005 görebilirsiniz.

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Bu derleyici seçeneğini Visual Studio'da ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Ekleme **/ZC: externconstexpr** veya **/Zc:externConstexpr-** için **ek seçenekler:** bölmesi.

## <a name="see-also"></a>Ayrıca Bkz.

[/ZC (Uyumluluk)](../../build/reference/zc-conformance.md)
[auto anahtar sözcüğü](../../cpp/auto-keyword.md)