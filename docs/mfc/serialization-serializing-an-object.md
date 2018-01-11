---
title: 'Seri hale getirme: bir nesneyi seri hale getirme | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- serializing objects [MFC]
- serialization [MFC], objects
- objects [MFC], serializing
ms.assetid: 1db772b1-ad55-4fcf-b133-126cca082510
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 37e688a3619cd203e61997999a9b7eb7651d73fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="serialization-serializing-an-object"></a>Seri hale getirme: Bir Nesneyi Seri Hale Getirme
Makaleyi [seri hale getirme: seri hale getirilebilir bir sınıf yapma](../mfc/serialization-making-a-serializable-class.md) seri hale getirilebilir bir sınıf yapma gösterilmektedir. Seri hale getirilebilir bir sınıf olduktan sonra bir dosya gelen ve bu sınıfın nesnelerini seri hale getirebilir bir [CArchive](../mfc/reference/carchive-class.md) nesnesi. Bu makalede açıklanmaktadır:  
  
-   [CArchive nesnesi ne olduğunu](../mfc/what-is-a-carchive-object.md).  
  
-   [CArchive oluşturmanın iki yolu](../mfc/two-ways-to-create-a-carchive-object.md).  
  
-   [CArchive kullanma <\< ve >> işleçleri](../mfc/using-the-carchive-output-and-input-operators.md).  
  
-   [Depolama ve bir arşiv CObjects yükleme](../mfc/storing-and-loading-cobjects-via-an-archive.md).  
  
 Seri hale getirilebilir belgeniz için arşiv veya açıkça oluşturmak framework sağlayabilirsiniz `CArchive` kendiniz nesne. Kullanarak bir dosya ile seri hale getirilebilir nesnenizin arasında veri aktarılabileceğini <\< ve >> işleçlerini `CArchive` veya çağırarak bazı durumlarda `Serialize` işlevinin bir `CObject`-türetilmiş sınıf.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Serileştirme](../mfc/serialization-in-mfc.md)

