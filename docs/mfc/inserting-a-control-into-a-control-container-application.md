---
title: 'ActiveX denetim kapsayıcıları: bir denetim kapsayıcısı uygulamasına denetim ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ActiveX control containers [MFC], inserting controls
- ActiveX controls [MFC], adding to projects
ms.assetid: bbb617ff-872f-43d8-b4d6-c49adb16b148
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f025c9fa564bcd37c585db6ea5c5cd0f5be83e0d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46432146"
---
# <a name="activex-control-containers-inserting-a-control-into-a-control-container-application"></a>ActiveX Denetim Kapsayıcıları: Bir Denetim Kapsayıcısı Uygulamasına Denetim Ekleme

Bir ActiveX denetimini ActiveX denetimi kapsayıcısı uygulamasından erişebilmeniz için önce kapsayıcı kullanılarak uygulama ActiveX denetimini eklemelisiniz [ActiveX denetimi Ekle](../windows/insert-activex-control-dialog-box.md) iletişim kutusu.

Bir ActiveX denetimini ActiveX denetimi kapsayıcısı projeye eklemek için bkz [görüntüleme ve iletişim kutusuna ActiveX denetimleri ekleme](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md).

Denetimi ekledikten sonra iletişim kutusu sınıfı için bir üye değişkeni (ActiveX denetim türündeki) eklemeniz gerekir. Bu yordamı hakkında daha fazla bilgi için bkz. [bir üye değişkeni ekleme](../ide/adding-a-member-variable-visual-cpp.md).

Üye değişkeni bir sınıf için bir sarmalayıcı sınıfı adlandırılan otomatik olarak oluşturulur ve projenize eklenir ekledikten sonra. Bu sınıf, Denetim kapsayıcısı ile eklenen denetimin arasında bir arabirim olarak kullanılır.

## <a name="see-also"></a>Ayrıca Bkz.

[ActiveX Denetim Kapsayıcıları](../mfc/activex-control-containers.md)

