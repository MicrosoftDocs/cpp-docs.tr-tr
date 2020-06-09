---
title: Veri Değişimi
ms.date: 11/04/2016
helpviewer_keywords:
- property sheets [MFC], data exchange
- exchanging data with property sheets [MFC]
- DDX (dialog data exchange) [MFC], property sheets
ms.assetid: 689f02d0-51a9-455b-8ffb-5b44f0aefa28
ms.openlocfilehash: 5be82567e02fd5e935d42f9eff5bdee20fa0d5a8
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84622701"
---
# <a name="exchanging-data"></a>Veri Değişimi

Çoğu iletişim kutusunda olduğu gibi, özellik sayfası ve uygulama arasındaki veri alışverişi, özellik sayfasının en önemli işlevlerinden biridir. Bu makalede, bu görevin nasıl yapılacağı açıklanır.

Özellik sayfası ile veri değişimi, özellik sayfasının bireysel Özellik sayfaları ile verileri değiş tokuş etmenizden bir şeydir. Bir özellik sayfasıyla verileri değiştirme yordamı, bir [CPropertyPage](reference/cpropertypage-class.md) nesnesi yalnızca özelleştirilmiş bir [CDialog](reference/cdialog-class.md) nesnesi olduğundan, bir iletişim kutusuyla veri alışverişi için aynıdır. Yordam, bir iletişim kutusundaki denetimler ve iletişim kutusu nesnesinin üye değişkenleri arasındaki verileri değiş tokuş eden, çerçevenin iletişim kutusu veri değişimi (DDX) özelliğinden yararlanır.

Özellik sayfası ve normal iletişim kutusuyla veri değişimi arasındaki önemli fark, özellik sayfasında birden fazla sayfa olduğundan, özellik sayfasındaki tüm sayfalarla veri alışverişi yapmanız gerekir. DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](dialog-data-exchange-and-validation.md).

Aşağıdaki örnek, bir özellik sayfasının görünümü ile iki sayfası arasında veri değiş tokuşu gösterir:

[!code-cpp[NVC_MFCDocView#4](codesnippet/cpp/exchanging-data_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Özellik sayfaları](property-sheets-mfc.md)
