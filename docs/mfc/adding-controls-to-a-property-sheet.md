---
title: Özellik sayfasına denetim ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [MFC], adding to property sheets
- property sheets, adding controls
ms.assetid: 24ad4c0b-c1db-4850-b9f0-34aae8d74571
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0783571ed77d3d8dfaca69edf06330e62d8e98d0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46398514"
---
# <a name="adding-controls-to-a-property-sheet"></a>Özellik Sayfasına Denetim Ekleme

Varsayılan olarak, bir özellik sayfası için özellik sayfaları, sekme dizini ve Tamam, iptal et ve Uygula düğmeleri pencere alanını ayırır. (İptal edin ve Uygula düğmeleri Tamam modelsiz bir özellik sayfası yok.) Özellik sayfası için başka denetimler ekleyebilirsiniz. Örneğin, bir önizleme penceresi geçerli ayarları aşağıdaki gibi harici bir nesneye uygulanan durumunda görünür kullanıcıya göstermek için özellik sayfası alan sağındaki ekleyebilirsiniz.

Özellik sayfası iletişim kutusunda denetimleri ekleyebileceğiniz `OnCreate` işleyici. Ek denetimleri genellikle destekleme özellik sayfası iletişim kutusunun boyutunu genişletme gerektirir. Temel sınıfı çağırmadan sonra **CPropertySheet::OnCreate**, çağrı [GetWindowRect](../mfc/reference/cwnd-class.md#getwindowrect) dikdörtgenin genişliğini ve yüksekliğini şu anda ayrılmış bir özellik sayfası pencerenin almak için genişletin boyutları ve çağrı [MoveWindow](../mfc/reference/cwnd-class.md#movewindow) özellik sayfası pencerenin boyutunu değiştirmek için.

## <a name="see-also"></a>Ayrıca Bkz.

[Özellik sayfaları](../mfc/property-sheets-mfc.md)<br/>
[CPropertyPage Sınıfı](../mfc/reference/cpropertypage-class.md)<br/>
[CPropertySheet Sınıfı](../mfc/reference/cpropertysheet-class.md)
