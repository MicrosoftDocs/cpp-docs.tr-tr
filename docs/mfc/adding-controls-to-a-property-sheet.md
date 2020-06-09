---
title: Özellik Sayfasına Denetim Ekleme
ms.date: 11/04/2016
helpviewer_keywords:
- controls [MFC], adding to property sheets
- property sheets, adding controls
ms.assetid: 24ad4c0b-c1db-4850-b9f0-34aae8d74571
ms.openlocfilehash: 527c0a5ef6e9dc4fcc9d7668c12e15ec956b0e70
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616066"
---
# <a name="adding-controls-to-a-property-sheet"></a>Özellik Sayfasına Denetim Ekleme

Varsayılan olarak, özellik sayfası özellik sayfaları, sekme dizini ve Tamam, Iptal ve Uygula düğmeleri için pencere alanını ayırır. (Kalıcı olmayan özellik sayfasında Tamam, Iptal et ve Uygula düğmeleri yoktur.) Daha fazla denetimi özellik sayfasına ekleyebilirsiniz. Örneğin, bir dış nesneye uygulandığında geçerli ayarların nasıl görüneceğine ilişkin kullanıcıyı göstermek için özellik sayfası alanının sağına bir önizleme penceresi ekleyebilirsiniz.

İşleyici içindeki Özellik sayfası iletişim kutusuna denetimler ekleyebilirsiniz `OnCreate` . Ek denetimleri konağa eklemek, genellikle özellik sayfası iletişim kutusunun boyutunu genişletmeyi gerektirir. **CPropertySheet:: OnCreate**temel sınıfını çağırdıktan sonra, geçerli olarak ayrılmış Özellik sayfası penceresinin genişliğini ve yüksekliğini almak Için [GetWindowRect](reference/cwnd-class.md#getwindowrect) çağırın, dikdörtgenin boyutlarını genişletin ve özellik sayfası penceresinin boyutunu değiştirmek için [MoveWindow](reference/cwnd-class.md#movewindow) öğesini çağırın.

## <a name="see-also"></a>Ayrıca bkz.

[Özellik sayfaları](property-sheets-mfc.md)<br/>
[CPropertyPage Sınıfı](reference/cpropertypage-class.md)<br/>
[CPropertySheet sınıfı](reference/cpropertysheet-class.md)
