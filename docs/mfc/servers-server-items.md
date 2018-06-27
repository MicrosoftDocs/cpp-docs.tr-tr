---
title: 'Sunucular: Sunucu öğeleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- server items, implementing
- servers [MFC], server items
- architecture [MFC], server-item
- server items
- OLE server applications [MFC], server items
ms.assetid: 28ba81a1-726a-4728-a52d-68bc7efd5a3c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 72cbf640f7886eac65762520ebc7c21f3906f0c0
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953093"
---
# <a name="servers-server-items"></a>Sunucular: Sunucu Öğeleri
Bir kullanıcı bir katıştırılmış veya bağlantılı OLE öğesi düzenleyebileceğiniz şekilde, bir kapsayıcı bir sunucu başlattığında, sunucu uygulaması bir "sunucu öğesi." oluşturur Türetilen bir sınıfın bir nesnesi sunucusu öğesini `COleServerItem`, sunucu belge kapsayıcı uygulaması arasında bir arabirim sağlar.  
  
 `COleServerItem` Sınıfı OLE tarafından genellikle kapsayıcısından isteklerine yanıt olarak adlandırılan birden fazla geçersiz kılınabilir üye işlevleri tanımlar. Sunucu öğeleri sunucu belgesinin veya tüm belgeyi parçası temsil edebilir. OLE öğe kapsayıcısı belgede katıştırıldığında, sunucu öğesi tüm sunucu belgeyi temsil eder. OLE öğesi bağlandığında, sunucu öğesini Sunucu belgesinin veya bağlantı bir bölümü veya bütün olup olmamasına bağlı olarak tüm belge parçası temsil edebilir.  
  
 İçinde [HIERSVR](../visual-cpp-samples.md) , örneğin, sunucu öğesi sınıfı örnek `CServerItem`, sınıfın bir nesnesi için bir işaretçi bir üyenin `CServerNode`. `CServerNode` Bir ağacıdır HIERSVR uygulamanın belge düğümü nesnesidir. Zaman `CServerNode` nesnesidir kök düğümü `CServerItem` nesnesi tüm belgeyi temsil eder. Zaman `CServerNode` nesnesi olan bir alt düğüm `CServerItem` nesnesi, belgenin bir bölümünü temsil eder. MFC OLE örnek bkz [HIERSVR](../visual-cpp-samples.md) bu etkileşimi ilişkin bir örnek.  
  
##  <a name="_core_implementing_server_items"></a> Sunucu öğeleri uygulama  
 Uygulamanız için "starter" kod üretmek için Uygulama Sihirbazı'nı kullanırsanız sunucu öğeleri starter kodunuzda dahil etmek için yapmanız gereken tek şey OLE seçenekler sayfası sunucu seçenekleri birini seçmek için. Sunucu öğeleri varolan bir uygulamaya ekliyorsanız, aşağıdaki adımları gerçekleştirin:  
  
#### <a name="to-implement-a-server-item"></a>Bir sunucu öğesini uygulamak için  
  
1.  Öğesinden bir sınıf türetin `COleServerItem`.  
  
2.  Türetilmiş sınıfta geçersiz `OnDraw` üye işlevi.  
  
     Framework çağrıları `OnDraw` meta dosyası OLE öğesi oluşturmak için. Kapsayıcı uygulama bu meta öğesi oluşturmak için kullanır. Uygulamanızın görünüm sınıfı ayrıca sahip bir `OnDraw` sunucu uygulaması etkin olduğunda öğeyi işlemek için kullanılan üye işlevi.  
  
3.  Geçersiz kılma uygulamak `OnGetEmbeddedItem` server belge sınıfınız için. Daha fazla bilgi için bkz: [sunucular: sunucu belgeleri uygulama](../mfc/servers-implementing-server-documents.md) ve MFC OLE örnek [HIERSVR](../visual-cpp-samples.md).  
  
4.  Sunucu öğesi sınıfınızın uygulamak `OnGetExtent` üye işlevi. Framework öğenin boyutunu almak için bu işlevi çağırır. Varsayılan uygulama hiçbir şey yapmaz.  
  
##  <a name="_core_a_tip_for_server.2d.item_architecture"></a> Sunucu öğesi mimarisi için bir ipucu  
 İçinde belirtildiği gibi [uygulama sunucu öğeleri](#_core_implementing_server_items), sunucu uygulamaları sağlayabilmelidir öğeleri sunucunun görünümü hem de kapsayıcı uygulama tarafından kullanılan meta dosyası işlenemiyor. Microsoft Foundation Class Kitaplığı'nın uygulama mimarisinde, görünüm sınıfı 's `OnDraw` üye işlevi, düzenlenirken öğesi oluşturur (bkz [CView::OnDraw](../mfc/reference/cview-class.md#ondraw) içinde *sınıf kitaplığı başvurusu* ). Sunucu öğesi'nin `OnDraw` tüm diğer durumlarda meta dosyası içine öğesi oluşturur (bkz [COleServerItem::OnDraw](../mfc/reference/coleserveritem-class.md#ondraw)).  
  
 Yardımcı işlevleri server belge sınıfınızda yazma ve bunları çağırma tarafından kod yinelenmesini önlemek `OnDraw` , Görünüm ve sunucu öğesi sınıflardaki işlevleri. MFC OLE örnek [HIERSVR](../visual-cpp-samples.md) bu strateji kullanır: işlevleri `CServerView::OnDraw` ve `CServerItem::OnDraw` çağırın `CServerDoc::DrawTree` öğesi oluşturmak için.  
  
 Görünüm ve öğe `OnDraw` üye işlevlerini farklı koşullar altında çizmek için. Görünüm gibi yakınlaştırma, seçim boyutunu ve azami ölçüde, kırpma ve kaydırma çubukları gibi kullanıcı arabirimi öğeleri olarak Etkenler dikkate almanız gerekir. Sunucu öğesini her zaman diğer taraftan, tüm OLE nesnesi çizer.  
  
 Daha fazla bilgi için bkz: [CView::OnDraw](../mfc/reference/cview-class.md#ondraw), [COleServerItem](../mfc/reference/coleserveritem-class.md), [COleServerItem::OnDraw](../mfc/reference/coleserveritem-class.md#ondraw), ve [COleServerDoc::OnGetEmbeddedItem](../mfc/reference/coleserverdoc-class.md#ongetembeddeditem)içinde *sınıf kitaplığı başvurusu*.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sunucular](../mfc/servers.md)

