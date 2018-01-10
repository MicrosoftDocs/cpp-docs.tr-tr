---
title: "/ZC:externConstexpr (etkinleştir extern constexpr değişkenler) | Microsoft Docs"
ms.custom: 
ms.date: 9/29/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /Zc:externConstexpr
dev_langs: C++
helpviewer_keywords:
- -Zc:externConstexpr compiler option (C++)
- extern constexpr variables (C++)
ms.assetid: 4da5e33a-2e4d-4ed2-8616-bd8f43265c27
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 84037e5e8a942d51175d97957d0c05bd6f4aa29d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="zcexternconstexpr-enable-extern-constexpr-variables"></a>/ZC:externConstexpr (etkinleştir extern constexpr değişkenler)

**/Zc:externConstexpr** derleyici seçeneği söyler C++ standardına uygun ve dış bağlantı için izin vermek için derleyici `constexpr` değişkenleri. Varsayılan olarak, Visual Studio her zaman sağlayan bir `constexpr` değişken iç bağlantı, belirttiğiniz olsa bile `extern` anahtar sözcüğü.

## <a name="syntax"></a>Sözdizimi

> /ZC:externConstexpr [-]

## <a name="remarks"></a>Açıklamalar

**/Zc:externConstexpr** derleyici seçeneği neden olan dış bağlantı kullanarak bildirilen değişkenlerin uygulamak derleyici `extern constexpr`. **/Zc:externConstexpr** Visual Studio 2017 güncelleştirme 15,5 başlangıç seçeneği kullanılabilir. Visual Studio ve varsayılan olarak eski sürümlerinde veya **/Zc:externConstexpr-** belirtilirse, Visual Studio geçerlidir iç bağlantı `constexpr` olsa bile değişkenleri `extern` anahtar sözcüğü kullanılır.

Üstbilgi dosyası bildirilen bir değişken içeriyorsa `extern constexpr`, işaretlenmesi gerekir [__declspec(selectany)](../../cpp/selectany.md) bağlantılı ikili tek bir örneğinde yinelenen bildirimler birleştirmek için. Aksi takdirde bağlayıcı hataları, örneğin, bir tanım kural ihlalleri için LNK2005 görebilirsiniz.

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Visual Studio'da Bu derleyici seçeneği ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Altında **yapılandırma özellikleri**, genişletin **C/C++** ve ardından **komut satırı**.

1. Ekleme **/Zc:externConstexpr** veya **/Zc:externConstexpr-** için **ek seçenekler:** bölmesi.

## <a name="see-also"></a>Ayrıca Bkz.

[/ZC (Uyumluluk)](../../build/reference/zc-conformance.md)  
[auto Anahtar Sözcüğü](../../cpp/auto-keyword.md)