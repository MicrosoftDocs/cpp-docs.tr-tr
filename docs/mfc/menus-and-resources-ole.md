---
title: "Menüler ve kaynaklar (OLE) | Microsoft Docs"
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
- OLE visual editing servers [MFC]
- status bars [MFC], OLE document applications
- visual editing [MFC], application menus and resources
- string tables [MFC], visual editing applications
- OLE containers [MFC], menus and resources
- OLE applications [MFC], menus and resources
- OLE server applications [MFC], menus and resources
- toolbars [MFC], OLE document applications
- string editing [MFC], visual editing applications
- server applications [MFC], OLE menus and resources
- applications [OLE], menus and resources
- menus [MFC], OLE document applications
- in-place activation [MFC], OLE menus and resources
- containers [MFC], OLE container applications
- OLE menus and resources [MFC]
ms.assetid: 52bfa086-7d3d-466f-94c7-c7061f3bdb3a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: efe0a5f6dae2cece571eddabc4094ebb87df175b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="menus-and-resources-ole"></a>Menüler ve Kaynaklar (OLE)
Bu grubun makalelerin menüleri ve kaynakları MFC OLE belge uygulamaları kullanımını açıklar.  
  
 OLE görsel düzenleme ek gereksinimler menü ve hangi hem kapsayıcı modlarında sayısı olduğundan OLE belge uygulamaları tarafından sağlanan diğer kaynakları yerleştirir ve sunucu (Bileşen) uygulamaları kullanmaya ve kullanılır. Örneğin, bir tam sunucu uygulaması bu üç modlarından birini çalıştırabilirsiniz:  
  
-   Tek başına.  
  
-   Yerinde bağlamında bir öğe kapsayıcı düzenlemek için.  
  
-   Genellikle ayrı bir pencerede kapsayıcısı bağlamı dışında bir öğe düzenleme için açma.  
  
 Bu, bir uygulamanın olası her modu için üç ayrı menü düzenlerini gerektirir. Hızlandırıcı tabloları, ayrıca her yeni modu için gereklidir. Bir kapsayıcı uygulaması olabilir veya yerinde etkinleştirme desteklemiyor olabilir; destekliyorsa, yeni bir menü yapısı gerekir ve Hızlandırıcı tabloları ilişkili.  
  
 Yerinde etkinleştirme kapsayıcı ve sunucu uygulamaları için menü, araç çubuğu ve durum çubuğu alanı anlaşmaları gerekir gerektirir. Tüm kaynaklar bu göz önünde tasarlanmalıdır. Makaleyi [menüler ve kaynaklar: menü birleştirme](../mfc/menus-and-resources-menu-merging.md) ayrıntı bu konuda ele alınmaktadır.  
  
 Bu sorunları nedeniyle, en fazla dört ayrı menüleri ve Hızlandırıcı tablosu kaynakları OLE belge uygulamaları Uygulama Sihirbazı'yla oluşturulmuş olabilir. Bunlar şu nedenlerden dolayı kullanılır:  
  
|Kaynak adı|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|  
|-------------------|---------|  
|**IDR_MAINFRAME**|Hiçbir dosya açıksa MDI uygulama veya bir SDI uygulamada açık dosyalar bağımsız olarak kullanılır. OLE dışı uygulamalarda kullanılan standart menü budur.|  
|**IDR_\<Proje > türü**|MDI uygulamada açık dosya varsa kullanılır. Bir uygulama bağımsız olarak çalışırken kullanılır. OLE dışı uygulamalarda kullanılan standart menü budur.|  
|**IDR_\<Proje > TYPE_SRVR_IP**|Bir nesne yerinde açık olduğunda sunucu veya kapsayıcı tarafından kullanılır.|  
|**IDR_\<Proje > TYPE_SRVR_EMB**|Yerinde etkinleştirme kullanmadan bir nesne açtıysanız bir sunucu uygulaması tarafından kullanılır.|  
  
 Bu kaynak adlarının her biri bir menü ve genellikle Hızlandırıcı tablosunu temsil eder. Uygulama Sihirbazı'nı oluşturulmaz MFC uygulamalarında benzer bir düzeni kullanılmalıdır.  
  
 Aşağıdaki makaleler kapsayıcıları, sunucuları ve yerinde etkinleştirme uygulanması için gerekli birleştirme menüsü ile ilgili konuları ele alınmıştır:  
  
-   [Menüler ve Kaynaklar: Kapsayıcı Ekleme](../mfc/menus-and-resources-container-additions.md)  
  
-   [Menüler ve Kaynaklar: Sunucu Ekleme](../mfc/menus-and-resources-server-additions.md)  
  
-   [Menüler ve Kaynaklar: Menü Birleştirme](../mfc/menus-and-resources-menu-merging.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE](../mfc/ole-in-mfc.md)

