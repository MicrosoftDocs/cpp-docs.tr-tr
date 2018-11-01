---
title: Veri Değişimi
ms.date: 11/04/2016
helpviewer_keywords:
- property sheets [MFC], data exchange
- exchanging data with property sheets [MFC]
- DDX (dialog data exchange) [MFC], property sheets
ms.assetid: 689f02d0-51a9-455b-8ffb-5b44f0aefa28
ms.openlocfilehash: 84e2ff9478cb3606bafb7f0408b7e2cc8fee2c00
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50569643"
---
# <a name="exchanging-data"></a>Veri Değişimi

Çoğu iletişim kutuları gibi olan özellik sayfası ve uygulama arasında veri alışverişi, özellik sayfasının en önemli işlevleri biridir. Bu makalede, bu görevi nasıl gerçekleştireceğinizi açıklar.

Bir özellik sayfası ile veri değişimi özellik sayfasının tek tek özellik sayfaları ile veri değişimi, aslında bir konudur. Özellik sayfası ile veri değişimi yordamı beri bir iletişim kutusu veri değişimi aynıdır bir [CPropertyPage](../mfc/reference/cpropertypage-class.md) nesnedir yalnızca özelleştirilmiş [CDialog](../mfc/reference/cdialog-class.md) nesne. Yordamı, bir iletişim kutusu ve üye değişkenleri iletişim kutusu nesnenin denetimlerin arasında veri framework'ün iletişim kutusu veri değişimi (DDX) özelliği, yararlanır.

Bir özellik sayfası ve normal bir iletişim kutusu veri değişimi arasındaki en önemli fark, özellik sayfasında tüm sayfaları ile veri değişimi gerekir böylece birden fazla sayfa özellik sayfası sahip olur. DDX hakkında daha fazla bilgi için bkz. [iletişim kutusu veri değişimi ve doğrulaması](../mfc/dialog-data-exchange-and-validation.md).

Aşağıdaki örnek bir görünümü ve bir özellik sayfası iki sayfaları arasında veri değiş tokuşu gösterilmektedir:

[!code-cpp[NVC_MFCDocView#4](../mfc/codesnippet/cpp/exchanging-data_1.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[Özellik sayfaları](../mfc/property-sheets-mfc.md)

