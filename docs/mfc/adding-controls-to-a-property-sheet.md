---
title: Özellik Sayfasına Denetim Ekleme
ms.date: 11/04/2016
helpviewer_keywords:
- controls [MFC], adding to property sheets
- property sheets, adding controls
ms.assetid: 24ad4c0b-c1db-4850-b9f0-34aae8d74571
ms.openlocfilehash: 07b384b2db36ae59d4de8b99d9c07396ce793979
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57296312"
---
# <a name="adding-controls-to-a-property-sheet"></a>Özellik Sayfasına Denetim Ekleme

Varsayılan olarak, bir özellik sayfası için özellik sayfaları, sekme dizini ve Tamam, iptal et ve Uygula düğmeleri pencere alanını ayırır. (İptal edin ve Uygula düğmeleri Tamam modelsiz bir özellik sayfası yok.) Özellik sayfası için başka denetimler ekleyebilirsiniz. Örneğin, bir önizleme penceresi geçerli ayarları aşağıdaki gibi harici bir nesneye uygulanan durumunda görünür kullanıcıya göstermek için özellik sayfası alan sağındaki ekleyebilirsiniz.

Özellik sayfası iletişim kutusunda denetimleri ekleyebileceğiniz `OnCreate` işleyici. Ek denetimleri genellikle destekleme özellik sayfası iletişim kutusunun boyutunu genişletme gerektirir. Temel sınıfı çağırmadan sonra **CPropertySheet::OnCreate**, çağrı [GetWindowRect](../mfc/reference/cwnd-class.md#getwindowrect) dikdörtgenin genişliğini ve yüksekliğini şu anda ayrılmış bir özellik sayfası pencerenin almak için genişletin boyutları ve çağrı [MoveWindow](../mfc/reference/cwnd-class.md#movewindow) özellik sayfası pencerenin boyutunu değiştirmek için.

## <a name="see-also"></a>Ayrıca bkz.

[Özellik sayfaları](../mfc/property-sheets-mfc.md)<br/>
[CPropertyPage Sınıfı](../mfc/reference/cpropertypage-class.md)<br/>
[CPropertySheet Sınıfı](../mfc/reference/cpropertysheet-class.md)
