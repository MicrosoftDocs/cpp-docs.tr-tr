---
title: İletişim Verisi Doğrulama
ms.date: 11/04/2016
helpviewer_keywords:
- validating data [MFC], message boxes
- data validation [MFC], dialog boxes
- dialog boxes [MFC], validating data
- validating data [MFC], dialog box data entry
- DDV (dialog data validation) [MFC]
- data validation [MFC], message boxes
ms.assetid: f070c309-2044-4ff2-8c92-1ec1ea84af58
ms.openlocfilehash: 99540214d1b903c66d350145c08ab657d12ef8f7
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616752"
---
# <a name="dialog-data-validation"></a>İletişim Verisi Doğrulama

[Iletişim kutusu veri değişimi](dialog-data-exchange.md)örneğinde gösterildiği gıbı, DDV işlevlerini çağırarak veri alışverişinin yanı sıra doğrulama belirtebilirsiniz. `DDV_MaxChars`Örnekteki çağrı, metin kutusu denetimine girilen dizenin 20 karakterden uzun olduğunu doğrular. DDV işlevi, genellikle doğrulama başarısız olursa kullanıcıyı bir ileti kutusuyla uyarır ve kullanıcının verileri yeniden girmesi için odağı sorunlu denetime koyar. Belirli bir denetim için bir DDV işlevinin, aynı denetim için DDX işlevinden hemen sonra çağrılması gerekir.

Ayrıca, kendi özel DDX ve DDV yordamlarınızı tanımlayabilirsiniz. Bu ve DDX ve DDV 'in diğer yönleri hakkında ayrıntılı bilgi için bkz. [MFC teknik açıklaması 26](tn026-ddx-and-ddv-routines.md).

[Üye değişkeni Ekleme Sihirbazı](../ide/add-member-variable-wizard.md) , sizin için veri EŞLEMESINDEKI tüm ddx ve ddv çağrılarını yazar.

## <a name="see-also"></a>Ayrıca bkz.

[İletişim Kutusu Veri Değişimi ve Doğrulaması](dialog-data-exchange-and-validation.md)<br/>
[MFC’de İletişim Kutularıyla çalışma](life-cycle-of-a-dialog-box.md)<br/>
[İletişim Kutusu Veri Değişimi](dialog-data-exchange.md)
