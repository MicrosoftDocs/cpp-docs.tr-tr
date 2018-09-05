---
title: ATL iletişim kutusu Sihirbazı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.dlg.overview
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding dialog resources
- ATL Dialog Wizard
ms.assetid: b0b9ace5-83c9-40d3-82c3-eb6293f10583
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fe3311e46ea28424717a0274fbe9e956610cdc54
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43767718"
---
# <a name="atl-dialog-wizard"></a>ATL iletişim kutusu Sihirbazı

Bu sihirbaz, türetilen bir ATL iletişim kutusu nesne projeye ekler [Caxdialogımpl](../../atl/reference/caxdialogimpl-class.md). Türetilen bir iletişim kutusu `CAxDialogImpl` ActiveX denetimlerini barındırabilir.

Sihirbaz varsayılan bir iletişim kutusu kaynağı **Tamam** ve **iptal** düğmeleri. İletişim kutusu kaynağı düzenleyemez ve ActiveX denetimleri kullanarak ekleme [iletişim kutusu Düzenleyicisi](../../windows/dialog-editor.md) kaynak görünümünde.

Sihirbazın üst bilgi dosyasına ekler bir [ileti eşlemesi](../../atl/message-maps-atl.md) ve varsayılan işleme bildirimleri, olaylar'ı tıklatın. Bkz: [iletişim kutusu uygulama](../../atl/implementing-a-dialog-box.md) ATL iletişim kutusu hakkında daha fazla bilgi.

**Kısa ad**  
ATL iletişim nesnenin kısaltılmış adını ayarlar. Bu alanları ayrı ayrı değiştirmediğiniz sürece sağladığınız adın sınıf adı ve dosya (.cpp ve .h) adlarını belirler.

`Class`  
Oluşturulacak sınıfın adını ayarlar. Bu ad, size sağlamak adına dayanarak **kısa ad**, 'C', tipik bir sınıf adı öneki öncesinde.

**.h dosyası**  
Yeni nesne sınıfı için üst bilgi dosyası adını ayarlar. Varsayılan olarak, bu ad, sağladığınız adın dayanır **kısa ad**. Dosya adı, tercih ettiğiniz bir konuma kaydedin veya mevcut bir dosyaya sınıf bildirimi eklemek için üç nokta düğmesine tıklayın. Var olan bir dosya seçerseniz, sihirbaz, seçili konuma dek tıklatın kaydedilmeyecektir **son** Sihirbazı'nda.

Sihirbazın bir dosyanın üzerine yazmaz. ' A tıkladığınızda, var olan bir dosya adı seçerseniz **son**, Sihirbazı sınıf bildirimi dosya içeriğini eklenmeyeceğini göstermek isteyip istemediğinizi sorar. Tıklayın **Evet** ; dosya eklemek için tıklatın **Hayır** sihirbaza dönmek ve başka bir dosya adı belirtin.

**.cpp dosyası**  
Yeni nesne sınıfı için uygulama dosyasının adını ayarlar. Varsayılan olarak, bu ad, sağladığınız adın dayanır **kısa ad**. Dosya adı, tercih ettiğiniz bir konuma kaydetmek için üç nokta düğmesine tıklayın. ' A kadar dosyasını seçili konuma kaydedilmez **son** Sihirbazı'nda.

Sihirbazın bir dosyanın üzerine yazmaz. ' A tıkladığınızda, var olan bir dosya adı seçerseniz **son**, Sihirbazı sınıf uygulaması dosya içeriğini eklenmeyeceğini göstermek isteyip istemediğinizi sorar. Tıklayın **Evet** ; dosya eklemek için tıklatın **Hayır** sihirbaza dönmek ve başka bir dosya adı belirtin.

## <a name="see-also"></a>Ayrıca Bkz.

[ATL iletişim kutusu](../../atl/reference/adding-an-atl-dialog-box.md)

