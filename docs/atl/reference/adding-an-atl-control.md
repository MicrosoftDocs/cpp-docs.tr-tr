---
title: ATL denetimi ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding controls
- controls [ATL], adding to projects
ms.assetid: 10223e7e-fdb7-4163-80c6-44aeafa8e6ce
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a996df63430a2d6b1942112122a1f185ba8f13de
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/08/2018
ms.locfileid: "48859607"
---
# <a name="adding-an-atl-control"></a>ATL denetimi ekleme

Bir kullanıcı arabirimi nesnesi arabirimleri için tüm olası kapsayıcıları destekleyen bir proje eklemek için bu sihirbazı kullanın. Bu arabirimler desteklemek için projenin ATL uygulamasını veya ATL desteği içeren bir MFC uygulaması olarak oluşturulmuş gerekir. Kullanabileceğiniz [ATL projesi Sihirbazı](../../atl/reference/atl-project-wizard.md) bir ATL uygulama oluşturmak için veya [MFC uygulamanıza bir ATL nesnesi eklemek](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) bir MFC uygulaması için ATL desteği uygulamak için.

## <a name="to-add-an-atl-control-to-your-project"></a>ATL denetimi projenize eklemek için

1. Her ikisinde **Çözüm Gezgini** veya [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code), ATL basit nesne eklemek istediğiniz proje adına sağ tıklayın.

1. Tıklayın **Ekle** kısayol menüsünü ve ardından **sınıfı Ekle**.

1. İçinde [sınıfı Ekle](../../ide/add-class-dialog-box.md) Şablonlar bölmesinde, iletişim kutusu **ATL denetimi**ve ardından **Ekle** görüntülenecek [ATL denetimi Sihirbazı](../../atl/reference/atl-control-wizard.md).

Kullanarak **ATL denetimi Sihirbazı**, üç tür denetim oluşturabilirsiniz:

- Standart bir denetimde

- Bileşik Denetim

- DHTML denetimi

Ayrıca, denetimin boyutunu azaltın ve seçerek çoğu kapsayıcı tarafından kullanılmayan arabirimleri Kaldır **en az bir denetim** üzerinde **seçenekleri** Sihirbazı sayfası.

## <a name="see-also"></a>Ayrıca Bkz.

[Bileşik Denetime İşlevsellik Ekleme](../../atl/adding-functionality-to-the-composite-control.md)<br/>
[ATL COM Nesnelerinin Temelleri](../../atl/fundamentals-of-atl-com-objects.md)   
