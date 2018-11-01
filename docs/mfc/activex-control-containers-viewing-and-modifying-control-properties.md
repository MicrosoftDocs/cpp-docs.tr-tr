---
title: 'ActiveX Denetim Kapsayıcıları: Denetim Özelliklerini Görüntüleme ve Değiştirme'
ms.date: 11/04/2016
helpviewer_keywords:
- properties [MFC], viewing and modifying
- ActiveX control containers [MFC], viewing and modifying properties
- resource editors, viewing and modifying ActiveX controls
- ActiveX controls [MFC], properties
- controls [MFC], properties
ms.assetid: 14ce5152-742b-4e0d-a9ab-c7b456e32918
ms.openlocfilehash: abddda015a80b21d941409044524e2f526b26f08
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50454952"
---
# <a name="activex-control-containers-viewing-and-modifying-control-properties"></a>ActiveX Denetim Kapsayıcıları: Denetim Özelliklerini Görüntüleme ve Değiştirme

Bir projeye bir ActiveX denetimi eklediğinizde, ActiveX denetimi tarafından desteklenen özelliklerini görüntülemek ve değiştirmek kullanışlıdır. Bu makalede, Visual C++ kaynak düzenleyicisinin Bunu yapmak için nasıl kullanılacağını açıklanmaktadır.

ActiveX denetimi kapsayıcı uygulamanızı katıştırılmış denetimleri kullanıyorsa, görüntüleyebilir ve sırasında kaynak düzenleyicide denetimin özelliklerini değiştirin. Kaynak Düzenleyicisi, tasarım sırasında ayarlanan özellik değerleri için de kullanabilirsiniz. Kaynak Düzenleyicisi sonra otomatik olarak bu değerleri projenin kaynak dosyasına kaydeder. Tüm denetim örneği sonra bu değerleri başlatılan özelliklerini olacaktır.

Bu yordam, projenize bir denetim ekledikten varsayar. Bilgi için [ActiveX denetim kapsayıcıları: denetim içine bir denetim kapsayıcı uygulaması ekleme](../mfc/inserting-a-control-into-a-control-container-application.md).

Denetimin özelliklerini görüntüleyerek ilk adımı, projenin iletişim şablona denetimi örneğini eklemektir.

### <a name="to-view-the-properties-of-a-control"></a>Bir denetimin özelliklerini görüntülemek için

1. Kaynak Görünümü'nde açın **iletişim** klasör.

1. Şablonunuzu ana iletişim kutusunu açın.

1. Kullanarak bir ActiveX denetimi Ekle **ActiveX denetimi Ekle** iletişim kutusu. Daha fazla bilgi için [görüntüleme ve iletişim kutusuna ActiveX denetimleri ekleme](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md).

1. İletişim kutusuna ActiveX denetimini seçin.

1. Özellikler penceresinden tıklayın **özellikleri** düğmesi.

Kullanım **özellikleri** değiştirin ve yeni özellikleri hemen test etmek için iletişim kutusu.

## <a name="see-also"></a>Ayrıca Bkz.

[ActiveX Denetim Kapsayıcıları](../mfc/activex-control-containers.md)

