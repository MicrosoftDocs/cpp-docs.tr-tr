---
title: 'ActiveX denetim kapsayıcıları: Görüntüleme ve denetim özelliklerini değiştirme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- properties [MFC], viewing and modifying
- ActiveX control containers [MFC], viewing and modifying properties
- resource editors, viewing and modifying ActiveX controls
- ActiveX controls [MFC], properties
- controls [MFC], properties
ms.assetid: 14ce5152-742b-4e0d-a9ab-c7b456e32918
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ef443442cb19b9aaca82b74a0a5d8c72098d5cc2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="activex-control-containers-viewing-and-modifying-control-properties"></a>ActiveX Denetim Kapsayıcıları: Denetim Özelliklerini Görüntüleme ve Değiştirme
Bir projeye bir ActiveX denetimi eklediğinizde, ActiveX denetimi tarafından desteklenen özelliklerini görüntülemek ve değiştirmek kullanışlıdır. Bu makalede, Visual C++ kaynak Düzenleyici Bunu yapmak için nasıl kullanılacağı açıklanmaktadır.  
  
 ActiveX denetimi kapsayıcısı uygulamanızı katıştırılmış denetimleri kullanıyorsa, görüntüleyin ve kaynak düzenleyicisinde sırada denetimin özelliklerini değiştirin. Tasarım zamanı sırasında özellik değerlerini ayarlamak için kaynak Düzenleyicisi'ni de kullanabilirsiniz. Kaynak Düzenleyici sonra otomatik olarak bu değerleri projenin kaynak dosyasında kaydeder. Herhangi bir örneğine denetim ardından bu değerleri başlatılmış özelliklerini sahip olur.  
  
 Bu yordam, projenize bir denetim eklediğiniz varsayar. Bilgi için bkz: [ActiveX denetimi kapsayıcıları: bir denetim içine bir denetim kapsayıcısı uygulamasına ekleme](../mfc/inserting-a-control-into-a-control-container-application.md).  
  
 Denetimin özelliklerini görüntüleyerek ilk adımı, projenin iletişim şablonu denetimi örneğini eklemektir.  
  
### <a name="to-view-the-properties-of-a-control"></a>Bir denetimin özelliklerini görüntülemek için  
  
1.  Kaynak Görünümü'nde açın **iletişim** klasör.  
  
2.  Ana iletişim kutusu şablonunuzu açın.  
  
3.  Kullanarak bir ActiveX denetimi Ekle **ActiveX denetimi Ekle** iletişim kutusu. Daha fazla bilgi için bkz: [görüntüleme ve ActiveX denetimlerine ekleme iletişim kutusu](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md).  
  
4.  ActiveX denetimi iletişim kutusunu seçin.  
  
5.  Özellikler penceresinden tıklatın **özellikleri** düğmesi.  
  
 Kullanım **özellikleri** değiştirin ve yeni özellikleri hemen test etmek için iletişim kutusu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ActiveX Denetim Kapsayıcıları](../mfc/activex-control-containers.md)

