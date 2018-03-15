---
title: /Zc:externConstexpr (Enable extern constexpr variables) | Microsoft Docs
ms.custom: 
ms.date: 02/28/2018
ms.technology:
- cpp-tools
ms.topic: article
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
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6597bc96609ab051df56886ccc580516986f97ed
ms.sourcegitcommit: eeb2b5ad8d3d22514a7b9bd7d756511b69ae0ccf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2018
---
# <a name="zcexternconstexpr-enable-extern-constexpr-variables"></a>/Zc:externConstexpr (Enable extern constexpr variables)

**/Zc:externConstexpr** derleyici seçeneği söyler C++ standardına uygun ve dış bağlantı için izin vermek için derleyici `constexpr` değişkenleri. Varsayılan olarak, Visual Studio her zaman sağlayan bir `constexpr` değişken iç bağlantı, belirttiğiniz olsa bile `extern` anahtar sözcüğü.

## <a name="syntax"></a>Sözdizimi

> **/Zc:externConstexpr**[**-**]

## <a name="remarks"></a>Açıklamalar

**/Zc:externConstexpr** derleyici seçeneği neden olan dış bağlantı kullanarak bildirilen değişkenlerin uygulamak derleyici `extern constexpr`. Visual Studio ve varsayılan olarak eski sürümlerinde veya **/Zc:externConstexpr-** belirtilirse, Visual Studio geçerlidir iç bağlantı `constexpr` olsa bile değişkenleri `extern` anahtar sözcüğü kullanılır. **/Zc:externConstexpr** Visual Studio 2017 güncelleştirme 15,6 başlangıç seçeneği kullanılabilir. ve varsayılan olarak kapalıdır. [/ İzin veren-](permissive-standards-conformance.md) seçeneği sağlamaz **/Zc:externConstexpr**.

Üstbilgi dosyası bildirilen bir değişken içeriyorsa `extern constexpr`, işaretlenmesi gerekir [__declspec(selectany)](../../cpp/selectany.md) bağlantılı ikili tek bir örneğinde yinelenen bildirimler birleştirmek için. Aksi takdirde bağlayıcı hataları, örneğin, bir tanım kural ihlalleri için LNK2005 görebilirsiniz.

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Visual Studio'da Bu derleyici seçeneği ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Ekleme **/Zc:externConstexpr** veya **/Zc:externConstexpr-** için **ek seçenekler:** bölmesi.

## <a name="see-also"></a>Ayrıca Bkz.

[/Zc (Uyumluluk)](../../build/reference/zc-conformance.md)  
[auto Anahtar Sözcüğü](../../cpp/auto-keyword.md)