---
description: 'Daha fazla bilgi edinin: ATL Iletişim kutusu Sihirbazı'
title: ATL İletişim Kutusu Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.dlg.overview
helpviewer_keywords:
- ATL projects, adding dialog resources
- ATL Dialog Wizard
ms.assetid: b0b9ace5-83c9-40d3-82c3-eb6293f10583
ms.openlocfilehash: 2fc110f12399c0c855cb98a9d7e505180bef7b0c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158887"
---
# <a name="atl-dialog-wizard"></a>ATL İletişim Kutusu Sihirbazı

Bu sihirbaz, [Caxdialogimpl](../../atl/reference/caxdialogimpl-class.md)'den TÜRETILMIŞ bir atl iletişim kutusu nesnesine projeye ekler. ' Dan türetilmiş bir iletişim kutusu `CAxDialogImpl` , ActiveX denetimlerini barındırabilir.

Sihirbaz varsayılan **Tamam** ve **iptal** düğmelerini kullanarak bir iletişim kutusu kaynağı oluşturur. İletişim kutusu kaynağını düzenleyebilir ve Kaynak Görünümü içindeki [Iletişim düzenleyicisini](../../windows/dialog-editor.md) kullanarak ActiveX denetimleri ekleyebilirsiniz.

Sihirbaz başlık dosyasına bir [ileti haritası](../../atl/message-maps-atl.md) ve varsayılan tıklama olaylarını işlemeye yönelik bildirimler ekler. ATL iletişim kutuları hakkında daha fazla bilgi için bkz. [Iletişim kutusu uygulama](../../atl/implementing-a-dialog-box.md) .

- **Kısa ad**

   ATL iletişim kutusu nesnesi için kısaltılmış adı ayarlar. Sağladığınız ad, bu alanları ayrı ayrı değiştirmediğiniz müddetçe sınıf adını ve dosya (. cpp ve. h) adlarını belirler.

- **Sınıf**

   Oluşturulacak sınıfın adını ayarlar. Bu ad, bir sınıf adı için tipik ön ek olan **kısa ad**' C ' ile verdiğiniz adı temel alır.

- **. h dosyası**

   Yeni nesnenin sınıfının başlık dosyasının adını ayarlar. Bu ad, varsayılan olarak, **kısa ad**'de sağladığınız adı temel alır. Dosya adını istediğiniz konuma kaydetmek veya sınıf bildirimini mevcut bir dosyaya eklemek için üç nokta düğmesini tıklatın. Var olan bir dosyayı seçerseniz, sihirbazda **son** ' a tıklaana kadar sihirbaz onu seçilen konuma kaydetmez.

   Sihirbaz bir dosyanın üzerine yazmaz. Mevcut bir dosyanın adını seçerseniz, **son**' a tıkladığınızda, sihirbaz sınıf bildiriminin dosya içeriğine eklenip eklenmeyeceğini belirtmek isteyip istemediğinizi sorar. Dosyayı eklemek için **Evet** ' e tıklayın; sihirbaza dönmek için **Hayır** ' a tıklayın ve başka bir dosya adı belirtin.

- **. cpp dosyası**

   Yeni nesnenin sınıfının uygulama dosyasının adını ayarlar. Bu ad, varsayılan olarak, **kısa ad**'de sağladığınız adı temel alır. Dosya adını istediğiniz konuma kaydetmek için üç nokta düğmesine tıklayın. Bu dosya, sihirbazda **son** ' a tıklaana kadar seçili konuma kaydedilmez.

   Sihirbaz bir dosyanın üzerine yazmaz. Mevcut bir dosyanın adını seçerseniz, **son**' a tıkladığınızda sihirbaz, sınıf uygulamasının dosyanın içeriğine eklenip eklenmeyeceğini belirtmek isteyip istemediğinizi sorar. Dosyayı eklemek için **Evet** ' e tıklayın; sihirbaza dönmek için **Hayır** ' a tıklayın ve başka bir dosya adı belirtin.

## <a name="see-also"></a>Ayrıca bkz.

[ATL Iletişim kutusu](../../atl/reference/adding-an-atl-dialog-box.md)
