---
title: 'ActiveX Denetim Kapsayıcıları: Bir Denetim Kapsayıcısı Uygulamasına Denetim Ekleme'
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX control containers [MFC], inserting controls
- ActiveX controls [MFC], adding to projects
ms.assetid: bbb617ff-872f-43d8-b4d6-c49adb16b148
ms.openlocfilehash: 1d2fc82628b3bcf842a6efb1d36ab9e8389fc0ba
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618491"
---
# <a name="activex-control-containers-inserting-a-control-into-a-control-container-application"></a>ActiveX Denetim Kapsayıcıları: Bir Denetim Kapsayıcısı Uygulamasına Denetim Ekleme

ActiveX Denetim kapsayıcısı uygulamasından bir ActiveX denetimine erişebilmek için, ActiveX denetimi [Ekle](../windows/insert-activex-control-dialog-box.md) iletişim kutusunu kullanarak, kapsayıcı uygulamasına ActiveX denetimini eklemeniz gerekir.

ActiveX Denetim kapsayıcısı projesine ActiveX denetimi eklemek için bkz. [bir Iletişim kutusuna ActiveX denetimleri görüntüleme ve ekleme](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md).

Denetimi eklediğinizde, iletişim kutusu sınıfına bir üye değişkeni (ActiveX denetim türü) eklemeniz gerekir. Bu yordam hakkında daha fazla bilgi için bkz. [üye değişkeni ekleme](../ide/adding-a-member-variable-visual-cpp.md).

Üye değişkenini ekledikten sonra sarmalayıcı sınıfı olarak adlandırılan bir sınıf otomatik olarak oluşturulur ve projenize eklenir. Bu sınıf, Denetim kapsayıcısı ve katıştırılmış denetim arasında bir arabirim olarak kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[ActiveX denetim kapsayıcıları](activex-control-containers.md)
