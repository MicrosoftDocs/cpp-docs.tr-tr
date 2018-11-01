---
title: ATL iletişim kutusu Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.dlg.overview
helpviewer_keywords:
- ATL projects, adding dialog resources
- ATL Dialog Wizard
ms.assetid: b0b9ace5-83c9-40d3-82c3-eb6293f10583
ms.openlocfilehash: 7f868800bb8453ac47ec0f188d6a2970aee7a55f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50458064"
---
# <a name="atl-dialog-wizard"></a>ATL iletişim kutusu Sihirbazı

Bu sihirbaz, türetilen bir ATL iletişim kutusu nesne projeye ekler [Caxdialogımpl](../../atl/reference/caxdialogimpl-class.md). Türetilen bir iletişim kutusu `CAxDialogImpl` ActiveX denetimlerini barındırabilir.

Sihirbaz varsayılan bir iletişim kutusu kaynağı **Tamam** ve **iptal** düğmeleri. İletişim kutusu kaynağı düzenleyemez ve ActiveX denetimleri kullanarak ekleme [iletişim kutusu Düzenleyicisi](../../windows/dialog-editor.md) kaynak görünümünde.

Sihirbazın üst bilgi dosyasına ekler bir [ileti eşlemesi](../../atl/message-maps-atl.md) ve varsayılan işleme bildirimleri, olaylar'ı tıklatın. Bkz: [iletişim kutusu uygulama](../../atl/implementing-a-dialog-box.md) ATL iletişim kutusu hakkında daha fazla bilgi.

- **Kısa ad**

   ATL iletişim nesnenin kısaltılmış adını ayarlar. Bu alanları ayrı ayrı değiştirmediğiniz sürece sağladığınız adın sınıf adı ve dosya (.cpp ve .h) adlarını belirler.

- **Sınıfı**

   Oluşturulacak sınıfın adını ayarlar. Bu ad, size sağlamak adına dayanarak **kısa ad**, 'C', tipik bir sınıf adı öneki öncesinde.

- **.h dosyası**

   Yeni nesne sınıfı için üst bilgi dosyası adını ayarlar. Varsayılan olarak, bu ad, sağladığınız adın dayanır **kısa ad**. Dosya adı, tercih ettiğiniz bir konuma kaydedin veya mevcut bir dosyaya sınıf bildirimi eklemek için üç nokta düğmesine tıklayın. Var olan bir dosya seçerseniz, sihirbaz, seçili konuma dek tıklatın kaydedilmeyecektir **son** Sihirbazı'nda.

   Sihirbazın bir dosyanın üzerine yazmaz. ' A tıkladığınızda, var olan bir dosya adı seçerseniz **son**, Sihirbazı sınıf bildirimi dosya içeriğini eklenmeyeceğini göstermek isteyip istemediğinizi sorar. Tıklayın **Evet** ; dosya eklemek için tıklatın **Hayır** sihirbaza dönmek ve başka bir dosya adı belirtin.

- **.cpp dosyası**

   Yeni nesne sınıfı için uygulama dosyasının adını ayarlar. Varsayılan olarak, bu ad, sağladığınız adın dayanır **kısa ad**. Dosya adı, tercih ettiğiniz bir konuma kaydetmek için üç nokta düğmesine tıklayın. ' A kadar dosyasını seçili konuma kaydedilmez **son** Sihirbazı'nda.

   Sihirbazın bir dosyanın üzerine yazmaz. ' A tıkladığınızda, var olan bir dosya adı seçerseniz **son**, Sihirbazı sınıf uygulaması dosya içeriğini eklenmeyeceğini göstermek isteyip istemediğinizi sorar. Tıklayın **Evet** ; dosya eklemek için tıklatın **Hayır** sihirbaza dönmek ve başka bir dosya adı belirtin.

## <a name="see-also"></a>Ayrıca Bkz.

[ATL iletişim kutusu](../../atl/reference/adding-an-atl-dialog-box.md)

