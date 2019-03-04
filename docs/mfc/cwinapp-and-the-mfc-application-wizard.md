---
title: CWinApp ve MFC Uygulama Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- CWinApp
helpviewer_keywords:
- application wizards [MFC], and CWinApp
- CWinApp class [MFC], and MFC Application Wizard
- MFC, wizards
ms.assetid: f8ac0491-3302-4e46-981d-0790624eb8a2
ms.openlocfilehash: cb45c8ffae15628b0b99a1ebcd962d88d845f83b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57266269"
---
# <a name="cwinapp-and-the-mfc-application-wizard"></a>CWinApp ve MFC Uygulama Sihirbazı

İskelet bir uygulama oluşturduğunda, MFC Uygulama Sihirbazı, bir uygulama sınıfı türetilen bildirir [CWinApp](../mfc/reference/cwinapp-class.md). MFC Uygulama Sihirbazı, aşağıdaki öğeleri içeren bir uygulama dosyasını da oluşturur:

- Uygulama sınıfı için ileti eşlemesi.

- Bir boş sınıf oluşturucu.

- Değişken yalnızca sınıf nesnesi bildirir.

- Standart bir uygulaması, `InitInstance` üye işlevi.

Proje başlığı ve ana kaynak dosyalarında uygulama sınıfı yerleştirilir. Oluşturulan dosyalar ve sınıf adları MFC Uygulama Sihirbazı'nda sağladığınız proje adı temel alır. Bu sınıfların kodunu görüntülemek için en kolay yolu aracılığıyladır [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code).

Standart uygulamalar ve sağlanan ileti eşlemesi birçok amaç için uygundur, ancak bunları gerektiği şekilde değiştirebilirsiniz. Bu uygulamalar en ilginç `InitInstance` üye işlevi. Genellikle, iskelet uygulanması için kod ekleyeceksiniz `InitInstance`.

## <a name="see-also"></a>Ayrıca bkz.

[CWinApp: Uygulama sınıfı](../mfc/cwinapp-the-application-class.md)<br/>
[Geçersiz Kılınabilir CWinApp Üye İşlevleri](../mfc/overridable-cwinapp-member-functions.md)<br/>
[Özel CWinApp Hizmetleri](../mfc/special-cwinapp-services.md)
