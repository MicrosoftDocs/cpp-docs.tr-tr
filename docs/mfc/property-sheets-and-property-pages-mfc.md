---
description: 'Daha fazla bilgi edinin: Özellik sayfaları ve özellik sayfaları (MFC)'
title: Özellik Bölümleri ve Özellik Sayfaları (MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], tabs
- property pages [MFC], property sheets
- CPropertyPage class [MFC], property sheets and pages
- CPropertySheet class [MFC], property sheets and pages
- property sheets, propert pages
ms.assetid: de8fea12-6c35-4cef-8625-b8073a379446
ms.openlocfilehash: 6819b890c699aeb428d2e0c76b048f5043e1dee7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248866"
---
# <a name="property-sheets-and-property-pages-mfc"></a>Özellik Bölümleri ve Özellik Sayfaları (MFC)

MFC [iletişim kutusu](../mfc/dialog-boxes.md) , özellik sayfaları ve özellik sayfaları ekleyerek bir "sekme iletişim kutusu" görünümünü alabilir. MFC 'de "özellik sayfası" olarak adlandırıldığından, Microsoft Word, Excel ve Visual C++ 'daki birçok iletişim kutusuna benzeyen bu tür bir iletişim kutusu, önde gelen dosya klasörlerinin bir yığınında veya basamaklı bir pencere grubundan benzer şekilde sekmeli bir yığın içeriyor gibi görünür. Ön sekmedeki denetimler görünür; arka sekmelerde yalnızca etiketli sekme görünür. Özellik sayfaları, çok sayıda özelliği veya çeşitli gruplara oldukça çok sayıda özelliği yönetmek için özellikle yararlıdır. Genellikle, bir özellik sayfası, birkaç ayrı iletişim kutusunu değiştirerek Kullanıcı arabirimini basitleştirebilir.

MFC sürüm 4,0 itibariyle, özellik sayfaları ve özellik sayfaları, Windows 95 ve Windows NT sürüm 3,51 ve sonraki sürümleriyle gelen ortak denetimler kullanılarak uygulanır.

Özellik sayfaları, [CPropertySheet](../mfc/reference/cpropertysheet-class.md) ve [CPropertyPage](../mfc/reference/cpropertypage-class.md) sınıfları Ile uygulanır ( *MFC başvurusunda* açıklanmıştır). `CPropertySheet` temelinde birden çok "sayfa" içerebilen genel iletişim kutusunu tanımlar `CPropertyPage` .

Özellik sayfaları oluşturma ve bunlarla çalışma hakkında daha fazla bilgi için, [Özellik sayfaları](../mfc/property-sheets-mfc.md)konusuna bakın.

## <a name="see-also"></a>Ayrıca bkz.

[İletişim kutuları](../mfc/dialog-boxes.md)<br/>
[MFC’de İletişim Kutularıyla çalışma](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[MFC 'de Özellik sayfaları ve özellik sayfaları](../mfc/property-sheets-and-property-pages-in-mfc.md)<br/>
[Veri değişimi](../mfc/exchanging-data.md)<br/>
[Kalıcı olmayan özellik sayfası oluşturma](../mfc/creating-a-modeless-property-sheet.md)<br/>
[Uygula düğmesini işleme](../mfc/handling-the-apply-button.md)
