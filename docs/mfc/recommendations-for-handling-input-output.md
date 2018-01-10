---
title: "Giriş-Çıkış işleme için öneriler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- I/O [MFC], about I/O
- file-based I/O options
- I/O [MFC]
- I/O [MFC], options
- I/O [MFC], file-based options
ms.assetid: d664b175-3b4a-40c3-b14b-39de6b12e419
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cc7fbb58aa1ac85c185756eb336737cbaf33a48e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="recommendations-for-handling-inputoutput"></a>Giriş/Çıkış İşleme için Öneriler
Veya dosya tabanlı g/ç kullanıp nasıl aşağıdaki karar ağacı sorulara yanıt üzerinde bağlıdır:  
  
 **Uygulamanızdaki birincil veri disk dosyasında bulunur**  
  
-   Evet, birincil veri disk dosyasında bulunur:  
  
     **Yapar uygulama Dosya Aç belleğe dosyanın tamamını okuyun ve geri dosyanın tamamını dosyasını kaydetmek için disk yazma**  
  
    -   Evet: Varsayılan MFC belge böyledir. Kullanım **CDocument** seri hale getirme.  
  
    -   Hayır: Bu genellikle dosyanın güncelleştirme işlem tabanlı bir durumdur. İşlem başına temelinde dosyasını güncelleştirin ve gerekmeyen **CDocument** seri hale getirme.  
  
-   Hayır, birincil veri disk dosyasında bulunan değil:  
  
     **Verileri bir ODBC veri kaynağında bulunan**  
  
    -   Evet, verileri bir ODBC veri kaynağında bulunur:  
  
         MFC'nin veritabanı desteği kullanın. Bu durumda standart MFC uygulaması içeren bir `CDatabase` makalesinde ele alındığı gibi nesne [MFC: belgeler ve görünümler ile veritabanı sınıflarını kullanarak](../data/mfc-using-database-classes-with-documents-and-views.md). Uygulamayı da okuma ve yazma bir yedek dosya — Uygulama Sihirbazı'nı "bir veritabanı görünümü ve dosya desteği" seçeneği amacı. Bu durumda, serileştirme için yardımcı dosyasını kullanırsınız.  
  
    -   Hayır, verileri bir ODBC veri kaynağında bulunan değil.  
  
         Bu durumda örnekleri: veri olmayan bir-ODBC DBMS; içinde bulunan OLE veya DDE gibi diğer bazı mekanizması aracılığıyla verilerini okur.  
  
         Böyle durumlarda, serileştirme kullanmaz ve uygulamanızı olmaz ve açık menü öğeleri kaydedin. Hala kullanmak isteyebileceği bir **CDocument** giriş temel olarak, yalnızca bir MFC ODBC uygulama belge depolamak için kullandığı `CRecordset` nesneleri. Ancak framework'ün varsayılan dosya Aç/Kaydet Belge Serileştirme kullanmaz.  
  
 Dosya menüsünde komutlar olarak kaydetme ve kaydedin, açık desteklemek için Belge Serileştirme çerçevesi sağlar. Seri hale getirme okur ve nesneleri dahil olmak üzere sınıfından türetilen verileri Yazar `CObject`, çok kalıcı depolama, normal bir disk dosyası. Serileştirme kullanımı kolaydır ve gereksinimlerinizi çoğunu sunar, ancak birçok veri erişimi uygulamaları uygun olabilir. Veri erişimi uygulamaları genellikle veri işlem başına temelinde güncelleştirin. Bunlar işlem yerine okuma ve aynı anda tüm veri dosyası yazılırken tarafından etkilenen kayıtlarını güncelleştirin.  
  
 Seri hale getirme hakkında daha fazla bilgi için bkz: [seri hale getirme](../mfc/serialization-in-mfc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Seri Hale Getirme: Seri Hale Getirme ile Veritabanı giriş/çıkış](../mfc/serialization-serialization-vs-database-input-output.md)
