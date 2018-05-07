---
title: İleti eşlemelerinin bulunduğu yer | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- macros, message map
- locating message maps
- message classes [MFC], finding
- message-map macros
ms.assetid: bf59fbc8-b222-42d3-b5d3-0a79aa3cb923
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 19dfaec7d97bed560665fce25c2ddf2cc816a483
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="where-to-find-message-maps"></a>İleti Eşlemelerinin Bulunduğu Yer
Uygulama Sihirbazı'nı yeni bir iskelet uygulaması oluşturduğunuzda Uygulama Sihirbazı'nı sizin için oluşturduğu her komut hedefi sınıfı için ileti eşlemesi yazar. Bu türetilmiş uygulama, belge, Görünüm ve çerçeve penceresi sınıfları içerir. Bu ileti eşlemeleri bazıları belirli iletiler ve önceden tanımlanmış komutlar için Uygulama Sihirbazı tarafından sağlanan girişleri zaten var ve bazı ekleyeceksiniz işleyicileri yalnızca yer tutucular içerir.  
  
 Sınıf ileti eşlemesi bulunur. Sınıfı için CPP dosya. Uygulama Sihirbazı'nı oluşturan temel ileti Eşlemleriyle Çalışma, Özellikler penceresini iletiler ve her sınıf işleyecek komutlar için girişleri eklemek için kullanın. Bazı girişler ekledikten sonra normal ileti eşlemesi şuna benzeyebilir:  
  
 [!code-cpp[NVC_MFCMessageHandling#1](../mfc/codesnippet/cpp/where-to-find-message-maps_1.cpp)]  
  
 İleti eşleme makroları koleksiyonunu içerir. İki makroları [begın_message_map](reference/message-map-macros-mfc.md#begin_message_map) ve [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map), ileti eşlemesi köşeli ayraç. Diğer makrolar gibi `ON_COMMAND`, ileti haritanın içeriğini doldurun.  
  
> [!NOTE]
>  İleti eşleme makroları noktalı virgülle izlenmeyen.  
  
 Yeni bir sınıf oluşturmak için sınıfı Ekle Sihirbazı'nı kullandığınızda, ileti eşlemesi için sınıf sağlar. Alternatif olarak, kaynak kodu Düzenleyicisi'ni kullanarak el ile bir ileti eşlemesi oluşturabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Framework'ün İleti Eşlemelerini Araması](../mfc/how-the-framework-searches-message-maps.md)

