---
title: "ATL iletişim Sihirbazı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vc.codewiz.class.atl.dlg.overview
dev_langs: C++
helpviewer_keywords:
- ATL projects, adding dialog resources
- ATL Dialog Wizard
ms.assetid: b0b9ace5-83c9-40d3-82c3-eb6293f10583
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6cdf16b3e82ce69fa06b3eacda8d7b48643fb3c6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="atl-dialog-wizard"></a>ATL iletişim Sihirbazı
Bu sihirbaz, türetilmiş bir ATL iletişim kutusu nesnesinin projeye ekler [CAxDialogImpl](../../atl/reference/caxdialogimpl-class.md). Bir iletişim kutusu türetilmiş `CAxDialogImpl` ActiveX denetimlerini barındırabilir.  
  
 Sihirbaz varsayılan bir iletişim kutusu kaynağı **Tamam** ve **iptal** düğmeler. İletişim kaynağını düzenleyin ve ActiveX denetimlerini kullanarak eklemek [iletişim kutusu Düzenleyicisi](../../windows/dialog-editor.md) kaynak görünümünde.  
  
 Sihirbaz üstbilgi dosyasına ekler bir [ileti eşlemesi](../../atl/message-maps-atl.md) ve varsayılan işlemek için bildirimler, olaylar'ı tıklatın. Bkz: [bir iletişim kutusu uygulama](../../atl/implementing-a-dialog-box.md) ATL iletişim kutuları hakkında daha fazla bilgi.  
  
 **Kısa ad**  
 ATL iletişim nesnesi kısaltılmış adını belirler. Bu alanlar ayrı ayrı değiştirmediğiniz sürece sağladığınız ad sınıf adı ve dosya (.cpp ve .h) adlarını belirler.  
  
 `Class`  
 Oluşturulacak sınıfın adını ayarlar. Bu ad, size sağlamak adına dayanarak **kısa ad**, öncesinde 'C', tipik bir sınıf adı öneki olarak.  
  
 **.h dosyası**  
 Yeni nesne sınıfı için üstbilgi dosyası adını ayarlar. Varsayılan olarak, bu ad, sağladığınız adının dayanır **kısa ad**. Dosya adı tercih ettiğiniz bir konuma kaydedin veya varolan bir dosyaya sınıf bildirimi eklemek için üç nokta düğmesini tıklatın. Varolan bir dosyanın seçerseniz, sihirbaz bunu seçili konuma dek tıklatın kaydedilmeyecektir **son** Sihirbazı'nda.  
  
 Sihirbaz, bir dosyanın üzerine değildir. ' I tıklattığınızda varolan bir dosyanın adını seçeneğini belirlerseniz **son**, sınıf bildirimi dosyasının içeriğini eklenmiş olup olmadığını belirtmek için Sihirbazı ister. Tıklatın **Evet** ; dosyayı eklemek için tıklatın **Hayır** sihirbaza geri dönmek ve başka bir dosya adı belirtin.  
  
 **.cpp dosyası**  
 Yeni nesne sınıfı için uygulama dosyasının adını ayarlar. Varsayılan olarak, bu ad, sağladığınız adının dayanır **kısa ad**. Dosya adı seçiminizi konuma kaydetmek için üç nokta düğmesini tıklatın. Tıklattığınız kadar dosya seçili konuma kaydedilmez **son** Sihirbazı'nda.  
  
 Sihirbaz, bir dosyanın üzerine değildir. ' I tıklattığınızda varolan bir dosyanın adını seçeneğini belirlerseniz **son**, sınıf uygulamasını dosyasının içeriğini eklenmiş olup olmadığını belirtmek için Sihirbazı ister. Tıklatın **Evet** ; dosyayı eklemek için tıklatın **Hayır** sihirbaza geri dönmek ve başka bir dosya adı belirtin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL iletişim kutusu](../../atl/reference/adding-an-atl-dialog-box.md)

