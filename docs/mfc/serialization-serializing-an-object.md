---
title: 'Seri hale getirme: bir nesneyi seri hale getirme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- serializing objects [MFC]
- serialization [MFC], objects
- objects [MFC], serializing
ms.assetid: 1db772b1-ad55-4fcf-b133-126cca082510
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3439857f14f4c4fa78aa2df3e3da8e5c8941938d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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

