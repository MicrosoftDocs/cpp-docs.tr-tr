---
title: Veri Değişimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- property sheets [MFC], data exchange
- exchanging data with property sheets [MFC]
- DDX (dialog data exchange) [MFC], property sheets
ms.assetid: 689f02d0-51a9-455b-8ffb-5b44f0aefa28
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e503bd9268423fbe63ec76de4bcb5443a7d52696
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33345826"
---
# <a name="exchanging-data"></a>Veri Değişimi
Çoğu iletişim kutuları gibi özellik sayfasında ve uygulama arasında veri alışverişi özellik sayfasının en önemli işlevleri biridir. Bu makalede, bu görevi gerçekleştirmek açıklar.  
  
 Bir özellik sayfası ile veri değişimi özellik sayfası tek tek özellik sayfaları ile veri değişimi, aslında bir konudur. Özellik sayfası ile veri değişimi yordamı beri bir iletişim kutusu veri değişimi aynıdır bir [CPropertyPage](../mfc/reference/cpropertypage-class.md) nesnesidir yalnızca özel [CDialog](../mfc/reference/cdialog-class.md) nesnesi. Yordam, bir iletişim kutusu ve üye değişkenleri iletişim kutusu nesnesinin denetimlerinde arasında veri alış verişleri framework'ün iletişim kutusu veri değişimi (DDX) özelliği, yararlanır.  
  
 Bir özellik sayfası ile normal iletişim kutusu veri değişimi arasındaki en önemli fark, özellik sayfasında tüm sayfaları ile veri değişimi gerekir böylece özellik sayfasını birden çok sayfa sahip olur. DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../mfc/dialog-data-exchange-and-validation.md).  
  
 Aşağıdaki örnek, bir görünüm ve özellik sayfasının iki sayfaları arasında veri değiş tokuşu gösterilmektedir:  
  
 [!code-cpp[NVC_MFCDocView#4](../mfc/codesnippet/cpp/exchanging-data_1.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özellik sayfaları](../mfc/property-sheets-mfc.md)

