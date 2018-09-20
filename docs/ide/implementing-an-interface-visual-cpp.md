---
title: Arabirimi uygulama (Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interfaces, implementing
ms.assetid: 72f8731b-7e36-45db-8b10-7ef211a773cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4227f566d655911553baeb5e8162f13bc9994130
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46395537"
---
# <a name="implementing-an-interface-visual-c"></a>Arabirimi Uygulama (Visual C++)

Bir arabirim uygulamak için bir projenin ATL desteği içeren bir MFC uygulaması olarak veya bir ATL COM uygulaması oluşturmuş olmanız gerekir. Kullanabileceğiniz [ATL projesi Sihirbazı](../atl/reference/atl-project-wizard.md) bir ATL uygulama oluşturmak için veya [MFC uygulamanıza bir ATL nesnesi eklemek](../mfc/reference/adding-atl-support-to-your-mfc-project.md) bir MFC uygulaması için ATL desteği uygulamak için.

Bir arabirim uygulamak için projeyi oluşturduktan sonra ATL nesneyi eklemeniz gerekir. Bkz [nesneler ekleme ve denetimleri için ATL projesinde](../atl/reference/adding-objects-and-controls-to-an-atl-project.md) , ATL projesine nesne eklemek sihirbazları listesi.

> [!NOTE]
>  ATL iletişim kutuları, ATL, performans nesneleri ve performans sayaçlarını kullanarak XML Web Hizmetleri Sihirbazı'nı desteklemez.

Varsa, [ATL denetimi ekleme](../atl/reference/adding-an-atl-control.md), varsayılan arabirimlerini, listelenen belirtebilirsiniz [arabirimleri](../atl/reference/interfaces-atl-control-wizard.md) sayfasında, Sihirbazı ve atlcom.h içinde tanımlanmış.

Nesne veya denetimi ekledikten sonra arabirim Uygulama Sihirbazı'nı kullanarak tüm kullanılabilir tür kitaplığında bulunan, diğer arabirim uygulayabilir.

Yeni bir arabirim ekliyorsanız, bu projenin .idl dosyasına el ile eklemelisiniz. Bkz: [ATL projesine yeni arabirim ekleme](../atl/reference/adding-a-new-interface-in-an-atl-project.md) daha fazla bilgi için.

### <a name="to-implement-an-interface"></a>Bir arabirim uygulamak için

1. Sınıf Görünümü'nde, ATL nesneniz için sınıf adına sağ tıklayın.

1. Tıklayın **Ekle** kısayol menüsünü ve ardından **arabirim uygulama** görüntülenecek [arabirim Uygulama Sihirbazı](../ide/implement-interface-wizard.md).

1. Uygun tür kitaplıklarından uygulamak ve arabirimleri seçin **son**.

1. Sınıf Görünümü'nde, nesnenin tabanları genişletin ve arabirimleri düğüm uygulanmıştır ve ardından kullanılabilir özelliklerini, yöntemlerini ve olaylarını görmek için arabirimin düğümünü genişletin arabirimini görmek için.

   > [!NOTE]
   > Ayrıca [Nesne Tarayıcısı](/visualstudio/ide/viewing-the-structure-of-code) arabirimin üyelerini incelemek için.

## <a name="see-also"></a>Ayrıca Bkz.

[COM arabirimi oluşturma](../ide/creating-a-com-interface-visual-cpp.md)<br>
[COM Arabirimini Düzenleme](../ide/editing-a-com-interface.md)