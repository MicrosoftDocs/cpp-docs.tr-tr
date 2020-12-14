---
description: 'Hakkında daha fazla bilgi edinin: Iletişim verileri doğrulama'
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
ms.openlocfilehash: 0e90aa54130a59b48058928f56d9d36644d5142b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261365"
---
# <a name="dialog-data-validation"></a>İletişim Verisi Doğrulama

[Iletişim kutusu veri değişimi](dialog-data-exchange.md)örneğinde gösterildiği gıbı, DDV işlevlerini çağırarak veri alışverişinin yanı sıra doğrulama belirtebilirsiniz. `DDV_MaxChars`Örnekteki çağrı, metin kutusu denetimine girilen dizenin 20 karakterden uzun olduğunu doğrular. DDV işlevi, genellikle doğrulama başarısız olursa kullanıcıyı bir ileti kutusuyla uyarır ve kullanıcının verileri yeniden girmesi için odağı sorunlu denetime koyar. Belirli bir denetim için bir DDV işlevinin, aynı denetim için DDX işlevinden hemen sonra çağrılması gerekir.

Ayrıca, kendi özel DDX ve DDV yordamlarınızı tanımlayabilirsiniz. Bu ve DDX ve DDV 'in diğer yönleri hakkında ayrıntılı bilgi için bkz. [MFC teknik açıklaması 26](tn026-ddx-and-ddv-routines.md).

[Üye değişkeni Ekleme Sihirbazı](../ide/adding-a-member-variable-visual-cpp.md#add-member-variable-wizard) , sizin için veri EŞLEMESINDEKI tüm ddx ve ddv çağrılarını yazar.

## <a name="see-also"></a>Ayrıca bkz.

[İletişim kutusu veri değişimi ve doğrulaması](dialog-data-exchange-and-validation.md)<br/>
[MFC’de İletişim Kutularıyla çalışma](life-cycle-of-a-dialog-box.md)<br/>
[İletişim Kutusu Veri Değişimi](dialog-data-exchange.md)
