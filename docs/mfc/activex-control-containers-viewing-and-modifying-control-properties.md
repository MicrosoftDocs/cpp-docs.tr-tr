---
title: 'ActiveX denetim kapsayıcıları: Denetim özelliklerini görüntüleme ve değiştirme'
ms.date: 11/04/2016
helpviewer_keywords:
- properties [MFC], viewing and modifying
- ActiveX control containers [MFC], viewing and modifying properties
- resource editors, viewing and modifying ActiveX controls
- ActiveX controls [MFC], properties
- controls [MFC], properties
ms.assetid: 14ce5152-742b-4e0d-a9ab-c7b456e32918
ms.openlocfilehash: 1d42820efd06c2ae52f5d1b22b0bdfb6335c4a89
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907801"
---
# <a name="activex-control-containers-viewing-and-modifying-control-properties"></a>ActiveX denetim kapsayıcıları: Denetim özelliklerini görüntüleme ve değiştirme

Bir projeye ActiveX denetimi eklediğinizde, ActiveX denetimi tarafından desteklenen özellikleri görüntülemek ve değiştirmek yararlıdır. Bu makalede, bunu yapmak için görsel C++ kaynak Düzenleyicisi 'nin nasıl kullanılacağı açıklanır.

ActiveX Denetim kapsayıcısı uygulamanız katıştırılmış denetimler kullanıyorsa, kaynak düzenleyicide denetimin özelliklerini görüntüleyebilir ve değiştirebilirsiniz. Tasarım zamanı sırasında özellik değerlerini ayarlamak için kaynak düzenleyicisini de kullanabilirsiniz. Daha sonra kaynak Düzenleyicisi bu değerleri projenin kaynak dosyasına otomatik olarak kaydeder. Daha sonra denetimin herhangi bir örneği, bu değerler için özellikleri başlatılır.

Bu yordam projenize bir denetim eklediğinizi varsayar. Daha fazla bilgi için [bkz. ActiveX denetim kapsayıcıları: Denetim kapsayıcısı uygulamasına](../mfc/inserting-a-control-into-a-control-container-application.md)denetim ekleme.

Denetimin özelliklerini görüntülemenin ilk adımı, bir denetimin örneğini projenin iletişim şablonuna eklemektir.

### <a name="to-view-the-properties-of-a-control"></a>Bir denetimin özelliklerini görüntülemek için

1. Kaynak Görünümü ' de, **iletişim** klasörünü açın.

1. Ana iletişim kutusu şablonunuzu açın.

1. **ActiveX denetimi Ekle** iletişim kutusunu kullanarak bir ActiveX denetimi ekleyin. Daha fazla bilgi için bkz. [bir Iletişim kutusuna ActiveX denetimleri görüntüleme ve ekleme](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md).

1. İletişim kutusunda ActiveX denetimini seçin.

1. **Özellikler** penceresinde **Özellikler** düğmesine tıklayın.

Yeni özellikleri hemen değiştirmek ve test etmek için **Özellikler** iletişim kutusunu kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[ActiveX Denetim Kapsayıcıları](../mfc/activex-control-containers.md)
