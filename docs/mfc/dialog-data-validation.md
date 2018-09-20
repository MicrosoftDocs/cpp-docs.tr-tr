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
ms.openlocfilehash: 83c1208d3001739ca78186972c629ea8a094c8d8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46430897"
---
# <a name="dialog-data-validation"></a>İletişim Verisi Doğrulama

Veri değişimi ek doğrulama DDV işlevleri çağırarak örnekte gösterildiği gibi belirtebilirsiniz [iletişim kutusu veri değişimi](../mfc/dialog-data-exchange.md). `DDV_MaxChars` Örnek çağrıda metin kutusu denetimine girilen dize 20 karakterden uzun olduğunu doğrular. Doğrulama başarısız olursa ve kullanıcı verileri yeniden girebilmek için odak sorunlu denetimde koyar DDV işlevi genellikle bir ileti kutusu ile kullanıcıyı uyarır. DDV işlevi belirli bir denetim için aynı denetim için hemen DDX işlevinden sonra çağrılmalıdır.

Ayrıca, kendi özel DDX ve DDV rutinleri tanımlayabilirsiniz. Bu ve diğer yönleri DDX ve DDV hakkında daha fazla bilgi için bkz: [MFC Teknik Notu 26](../mfc/tn026-ddx-and-ddv-routines.md).

[Ekleme üye değişkeni Sihirbazı](../ide/add-member-variable-wizard.md) tüm DDX yazılır ve DDV, verilerin haritada çağırır.

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutusu Veri Değişimi ve Doğrulaması](../mfc/dialog-data-exchange-and-validation.md)<br/>
[Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[İletişim Kutusu Veri Değişimi](../mfc/dialog-data-exchange.md)

