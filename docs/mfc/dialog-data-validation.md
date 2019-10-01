---
title: İletişim kutusu verileri doğrulaması
ms.date: 11/04/2016
helpviewer_keywords:
- validating data [MFC], message boxes
- data validation [MFC], dialog boxes
- dialog boxes [MFC], validating data
- validating data [MFC], dialog box data entry
- DDV (dialog data validation) [MFC]
- data validation [MFC], message boxes
ms.assetid: f070c309-2044-4ff2-8c92-1ec1ea84af58
ms.openlocfilehash: c89ed82b148062ddb64fa85eaabda12f44e59895
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685767"
---
# <a name="dialog-data-validation"></a>İletişim kutusu verileri doğrulaması

[Iletişim kutusu veri değişimi](../mfc/dialog-data-exchange.md)örneğinde gösterildiği gıbı, DDV işlevlerini çağırarak veri alışverişinin yanı sıra doğrulama belirtebilirsiniz. Örnekteki `DDV_MaxChars` çağrısı, metin kutusu denetimine girilen dizenin 20 karakterden uzun olduğunu doğrular. DDV işlevi, genellikle doğrulama başarısız olursa kullanıcıyı bir ileti kutusuyla uyarır ve kullanıcının verileri yeniden girmesi için odağı sorunlu denetime koyar. Belirli bir denetim için bir DDV işlevinin, aynı denetim için DDX işlevinden hemen sonra çağrılması gerekir.

Ayrıca, kendi özel DDX ve DDV yordamlarınızı tanımlayabilirsiniz. Bu ve DDX ve DDV 'in diğer yönleri hakkında ayrıntılı bilgi için bkz. [MFC teknik açıklaması 26](../mfc/tn026-ddx-and-ddv-routines.md).

[Üye değişkeni Ekleme Sihirbazı](../ide/add-member-variable-wizard.md) , sizin için veri EŞLEMESINDEKI tüm ddx ve ddv çağrılarını yazar.

## <a name="see-also"></a>Ayrıca bkz.

[İletişim kutusu veri değişimi ve doğrulaması](../mfc/dialog-data-exchange-and-validation.md)<br/>
[MFC 'de Iletişim kutularıyla çalışma](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[İletişim kutusu veri değişimi](../mfc/dialog-data-exchange.md)
