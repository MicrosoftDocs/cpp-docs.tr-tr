---
title: İletişim verisi doğrulama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- validating data [MFC], message boxes
- data validation [MFC], dialog boxes
- dialog boxes [MFC], validating data
- validating data [MFC], dialog box data entry
- DDV (dialog data validation) [MFC]
- data validation [MFC], message boxes
ms.assetid: f070c309-2044-4ff2-8c92-1ec1ea84af58
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 229b4a5ffb32f4a167dcc8393a269bbb2e35b500
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33344886"
---
# <a name="dialog-data-validation"></a>İletişim Verisi Doğrulama
Veri değişimi ek doğrulama DDV işlevlerini çağırarak örnekte gösterildiği gibi belirtebilirsiniz [iletişim kutusu veri değişimi](../mfc/dialog-data-exchange.md). `DDV_MaxChars` Örnek çağrısında doğrular, metin kutusu denetimi girilen dize 20 karakterden uzun değil. Doğrulama başarısız olursa ve kullanıcı verileri yeniden girebilmek için sorunlu denetimi odağı koyar DDV işlevi genellikle bir ileti kutusu kullanıcıyla uyarır. Belirli bir denetim için DDV işlevi hemen sonra DDX işlevi için aynı denetim çağrılmalıdır.  
  
 Ayrıca, kendi özel DDX ve DDV rutinleri tanımlayabilirsiniz. Bu ve diğer yönlerini DDX ve DDV hakkında daha fazla bilgi için bkz: [MFC Teknik Not 26](../mfc/tn026-ddx-and-ddv-routines.md).  
  
 [Üye değişkeni ekleme](../ide/add-member-variable-wizard.md) tüm DDX yazılır ve DDV sizin için veri eşlemesinde çağırır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutusu veri değişimi ve doğrulaması](../mfc/dialog-data-exchange-and-validation.md)   
 [İletişim kutusunun yaşam döngüsü](../mfc/life-cycle-of-a-dialog-box.md)   
 [İletişim Kutusu Veri Değişimi](../mfc/dialog-data-exchange.md)

