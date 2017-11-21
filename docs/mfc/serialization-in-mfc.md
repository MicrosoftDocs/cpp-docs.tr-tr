---
title: MFC'de seri hale getirme | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- collection classes [MFC], serialization
- bypassing serialization [MFC]
- MFC, serialization
- serialization [MFC], MFC
- serialization [MFC], bypassing
ms.assetid: fb596a18-4522-47e0-96e0-192732d24c12
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d5c60fd4ff47745e5209023783b74f52a319065d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="serialization-in-mfc"></a>MFC'de Seri Hale Getirme
Bu makalede, Microsoft Foundation Class Kitaplığı (arasında kalıcı nesnelere izin vermek için MFC) sağlanan seri hale getirme mekanizmasını, programı çalıştıran açıklanmaktadır.  
  
 Serileştirme için veya bir nesne okuma veya yazma gibi bir disk dosyası kalıcı depolama ortamına gelen işlemidir. Seri hale getirme, burada sırasında veya sonrasında bir programın yürütülmesini (örneğin, C++ sınıfları veya yapıları) yapılandırılmış veri durumunu korumak için istendiğini durumlar için idealdir. MFC tarafından sağlanan seri hale getirme nesnelerini kullanarak bu el ile olarak dosya işlemleri için gereken kullanıcıdan gereksinimini azaltır standart ve tutarlı bir şekilde gerçekleşmesini sağlar.  
  
 MFC sınıf serileştirme için yerleşik destek sağlayan `CObject`. Bu nedenle, tüm türetilmiş sınıflar `CObject` yararlanabilir `CObject`'s serileştirme protokolü.  
  
 Temel serileştirme bir nesneyi kalıcı depolama birimine üye değişkenlerini değerini genellikle belirttiği geçerli durumuna yazabilmesi olması gerektiğini olur. Daha sonra nesne tarafından okuma veya seri durumdan, depolama biriminden nesnenin durumu yeniden oluşturulabilir. Seri hale getirme nesne işaretçileri ve bir nesneyi serileştirme sırasında kullanılan nesneleri dairesel başvurular tüm ayrıntılarını işler. Bir anahtar nesnenin okuma ve yazma kendi durumuna sorumlu olduğunu noktasıdır. Bu nedenle, seri hale getirilebilir bir sınıf için temel seri hale getirme işlemlerinin uygulamalıdır. Makaleler serileştirme grubunda gösterildiği gibi bu işlev bir sınıfa eklemek kolaydır.  
  
 MFC kullanan bir nesne `CArchive` serileştirilmesi için nesne ve depolama ortamına arasında bir aracı gibi sınıfı. Bu nesne her zaman ile ilişkili bir `CFile` nesne, seri hale getirme, dosya adı dahil olmak üzere gerekli bilgileri alır ve istenen işlem bir okuma veya yazma olup. Seri hale getirme işlemi gerçekleştiren nesnenin kullanabilirsiniz `CArchive` depolama ortamına yapısını dikkate almaksızın nesnesi.  
  
 A `CArchive` nesnesini kullanan aşırı yüklenmiş ekleme (**<\<**) ve ayıklama (**>>**) yazma ve okuma işlemlerini gerçekleştirmek için işleçler. Daha fazla bilgi için bkz: [saklama ve bir Arşiv yüklenirken Cobject'leri](../mfc/storing-and-loading-cobjects-via-an-archive.md) makalede seri hale getirme: bir nesneyi seri hale getirme.  
  
> [!NOTE]
>  Aynı şey `CArchive` içindir genel amaçlı iostream sınıfları sınıfıyla biçimlendirilmiş yalnızca metin. `CArchive` İkili biçime serileştirilmiş nesneler için bir sınıftır.  
  
 İsterseniz, kalıcı veri depolama için kendi mekanizması oluşturmak için MFC serileştirilmesi atlayabilirsiniz. Seri hale getirme kullanıcının komut başlatmak sınıf üye işlevlerini geçersiz kılmak gerekir. Tartışmada bkz [Teknik Not 22](../mfc/tn022-standard-commands-implementation.md) , `ID_FILE_OPEN`, **ıd_fıle_save**, ve **ıd_fıle_save_as** standart komutları.  
  
 Aşağıdaki makaleler seri hale getirme için gereken iki ana görevleri kapsar:  
  
-   [Seri hale getirme: seri hale getirilebilir bir sınıf yapma](../mfc/serialization-making-a-serializable-class.md)  
  
-   [Seri hale getirme: bir nesneyi seri hale getirme](../mfc/serialization-serializing-an-object.md)  
  
 Makaleyi [seri hale getirme: seri hale getirme vs. Veritabanı giriş/çıkış](../mfc/serialization-serialization-vs-database-input-output.md) serileştirme uygun bir giriş/çıkış teknik veritabanı uygulamalarında olduğunda açıklar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../mfc/mfc-concepts.md)   
 [Genel MFC konuları](../mfc/general-mfc-topics.md)   
 [CArchive sınıfı](../mfc/reference/carchive-class.md)   
 [CObject sınıfı](../mfc/reference/cobject-class.md)   
 [CDocument sınıfı](../mfc/reference/cdocument-class.md)   
 [CFile sınıfı](../mfc/reference/cfile-class.md)
