---
description: 'Hakkında daha fazla bilgi edinin: Özellik sayfasına denetim ekleme'
title: Özellik Sayfasına Denetim Ekleme
ms.date: 11/04/2016
helpviewer_keywords:
- controls [MFC], adding to property sheets
- property sheets, adding controls
ms.assetid: 24ad4c0b-c1db-4850-b9f0-34aae8d74571
ms.openlocfilehash: e220d08b46f1db7e09ad1f1398731ce7a98f2dc5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339070"
---
# <a name="adding-controls-to-a-property-sheet"></a>Özellik Sayfasına Denetim Ekleme

Varsayılan olarak, özellik sayfası özellik sayfaları, sekme dizini ve Tamam, Iptal ve Uygula düğmeleri için pencere alanını ayırır. (Kalıcı olmayan özellik sayfasında Tamam, Iptal et ve Uygula düğmeleri yoktur.) Daha fazla denetimi özellik sayfasına ekleyebilirsiniz. Örneğin, bir dış nesneye uygulandığında geçerli ayarların nasıl görüneceğine ilişkin kullanıcıyı göstermek için özellik sayfası alanının sağına bir önizleme penceresi ekleyebilirsiniz.

İşleyici içindeki Özellik sayfası iletişim kutusuna denetimler ekleyebilirsiniz `OnCreate` . Ek denetimleri konağa eklemek, genellikle özellik sayfası iletişim kutusunun boyutunu genişletmeyi gerektirir. **CPropertySheet:: OnCreate** temel sınıfını çağırdıktan sonra, geçerli olarak ayrılmış Özellik sayfası penceresinin genişliğini ve yüksekliğini almak Için [GetWindowRect](reference/cwnd-class.md#getwindowrect) çağırın, dikdörtgenin boyutlarını genişletin ve özellik sayfası penceresinin boyutunu değiştirmek için [MoveWindow](reference/cwnd-class.md#movewindow) öğesini çağırın.

## <a name="see-also"></a>Ayrıca bkz.

[Özellik sayfaları](property-sheets-mfc.md)<br/>
[CPropertyPage sınıfı](reference/cpropertypage-class.md)<br/>
[CPropertySheet sınıfı](reference/cpropertysheet-class.md)
