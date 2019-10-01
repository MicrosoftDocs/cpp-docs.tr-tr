---
title: Özellik sayfaları ve özellik sayfaları (MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], tabs
- property pages [MFC], property sheets
- CPropertyPage class [MFC], property sheets and pages
- CPropertySheet class [MFC], property sheets and pages
- property sheets, propert pages
ms.assetid: de8fea12-6c35-4cef-8625-b8073a379446
ms.openlocfilehash: 5d4fd1c957b7f4d0d6ad10379a448309743aa11a
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685085"
---
# <a name="property-sheets-and-property-pages-mfc"></a>Özellik sayfaları ve özellik sayfaları (MFC)

MFC [iletişim kutusu](../mfc/dialog-boxes.md) , özellik sayfaları ve özellik sayfaları ekleyerek bir "sekme iletişim kutusu" görünümünü alabilir. MFC 'de "özellik sayfası" olarak adlandırıldığından, Microsoft Word, Excel ve Visual C++'daki birçok iletişim kutusuna benzer bir dizi iletişim kutusu, önde gelen dosya klasörlerinin bir yığınında veya bir basamaklı pencere grubundan benzer şekilde sekmeli bir yığın içeriyor gibi görünür. Ön sekmedeki denetimler görünür; arka sekmelerde yalnızca etiketli sekme görünür. Özellik sayfaları, çok sayıda özelliği veya çeşitli gruplara oldukça çok sayıda özelliği yönetmek için özellikle yararlıdır. Genellikle, bir özellik sayfası, birkaç ayrı iletişim kutusunu değiştirerek Kullanıcı arabirimini basitleştirebilir.

MFC sürüm 4,0 itibariyle, özellik sayfaları ve özellik sayfaları, Windows 95 ve Windows NT sürüm 3,51 ve sonraki sürümleriyle gelen ortak denetimler kullanılarak uygulanır.

Özellik sayfaları, [CPropertySheet](../mfc/reference/cpropertysheet-class.md) ve [CPropertyPage](../mfc/reference/cpropertypage-class.md) sınıfları Ile uygulanır ( *MFC başvurusunda*açıklanmıştır). `CPropertySheet`, `CPropertyPage` ' i temel alan birden çok "sayfa" içerebilen genel iletişim kutusunu tanımlar.

Özellik sayfaları oluşturma ve bunlarla çalışma hakkında daha fazla bilgi için, [Özellik sayfaları](../mfc/property-sheets-mfc.md)konusuna bakın.

## <a name="see-also"></a>Ayrıca bkz.

[İletişim kutuları](../mfc/dialog-boxes.md)<br/>
[MFC 'de Iletişim kutularıyla çalışma](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[MFC 'de Özellik sayfaları ve özellik sayfaları](../mfc/property-sheets-and-property-pages-in-mfc.md)<br/>
[Veri değişimi](../mfc/exchanging-data.md)<br/>
[Kalıcı olmayan özellik sayfası oluşturma](../mfc/creating-a-modeless-property-sheet.md)<br/>
[Uygula düğmesini işleme](../mfc/handling-the-apply-button.md)
