---
title: "Etkin belge kapsaması | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- active documents [MFC], containers
- containers [MFC], active document
- MFC, COM support
- active document containers [MFC], about active document containers
- MFC COM, active document containment
ms.assetid: b8dfa74b-75ce-47df-b75e-fc87b7f7d687
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 16c0311c3eedc13cbc47214b44fc8810dee3eecd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="active-document-containment"></a>Etkin Belge Kapsaması
Etkin belge kapsaması belgelerle oluşturmak ve her belge türü için birden çok uygulama çerçeveleri kullanmak için zorlama yerine çalışmak üzere tek bir çerçeve sağlayan bir teknolojidir. OLE katıştırılmış nesneler yalnızca tek bir içerik etkinleştirilebilir bileşik belge içinde çalışır, temel OLE teknolojisini farklıdır. Etkin belge kapsaması ile tek bir çerçevesi bağlamında tüm belgeyi (ilişkili menüleri, araç çubukları ve benzeri dahil olmak üzere diğer bir deyişle, tüm uygulamanın) etkinleştirin.  
  
 Etkin belge kapsama teknolojisi ilk olarak Microsoft Office Office Binder uygulamak geliştirilmiştir. Ancak, teknolojinin etkin belge kapsayıcıları Office Binder dışında desteklemek için yeterince esnektir ve belge sunucuları Office ve Office uyumlu uygulamalar dışında destekleyebilir.  
  
 Etkin belgeler barındıran uygulama adlı bir [etkin belge kapsayıcısı](../mfc/active-document-containers.md). Microsoft Office Binder ya da Microsoft Internet Explorer gibi kapsayıcıları örnekleridir.  
  
 Etkin belge kapsaması OLE uzantılar kümesi, belgeler gibi OLE bileşik belge teknolojisinin uygulanır. Tek bir katıştırılmış içerik yerine tüm bir belgeyi temsil etmek gömülebilir, yerinde bir nesne izin ek arabirimleri uzantılarıdır. OLE belgeleri gibi etkin belge kapsaması etkin belgeler ve kullanıcı arabirimi ve işleme özelliklerini etkin belgeler için kendilerini sağlayan sunucuları için görüntü alanını sağlayan kapsayıcı kullanır.  
  
 Bir [etkin belge sunucusu](../mfc/active-document-servers.md) burada her nesne destekleyen nesne içinde etkinleştirilmesi izin uzantısı arabirimlerini etkin belge sınıfları, bir veya daha fazla destekleyen bir uygulamanız (örneğin, Word, Excel veya PowerPoint) olan bir uygun kapsayıcı.  
  
 Bir [etkin belgeyi](../mfc/active-documents.md) (Word veya Excel gibi etkin belgeyi sunucusundan sağlanır), başka bir etkin belge kapsayıcı içindeki bir nesne olarak katıştırılır temelde çözümlerinden, geleneksel belgedir. Katıştırılmış nesneler aksine etkin belgeler kendi sayfaları üzerinde tam denetime sahip ve uygulamayla (tüm temel komutları ve araçları) tam arabiriminin düzenlemek için kullanıcı tarafından kullanılabilir.  
  
 Etkin belge bir standart OLE katıştırılmış nesneden ayrım tarafından en iyi anlaşılmalıdır. OLE kuralı aşağıdaki katıştırılmış nesne sahibi belge sayfasında görüntülenen biridir ve belgenin OLE kapsayıcı tarafından yönetilir. Kapsayıcı belgenin geri kalanında ile katıştırılmış nesne verilerini depolar. Ancak, katıştırılmış nesneler üzerinde göründükleri sayfa kontrol etmez, sınırlıdır.  
  
 Etkin belge kapsayıcı uygulaması kullanıcılarının etkin belgeler (Office Binder bölümlerde adı verilir) oluşturabilirsiniz (Bu uygulamaları etkin belgeyi etkin olması koşuluyla) kullanarak kendi sık kullanılan uygulamalar, kullanıcılar sonuç projesi olarak yönetebilir henüz bir Yazdırılan vb. benzersiz olarak adlandırılan tek bir varlık kaydedildi. Aynı şekilde, bir kullanıcı bir Internet tarayıcısı, yerel dosya sistemleri, yanı sıra tüm ağ tek bir belge depolama varlık tek bir konumdan bu depolama belgelerde Gözat olanağı olarak davranabilirsiniz.  
  
## <a name="sample-programs"></a>Örnek programlar  
  
-   [MFCBIND](../visual-cpp-samples.md) örneği etkin belge kapsayıcı uygulaması uyarlamasını gösterir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC COM](../mfc/mfc-com.md)

