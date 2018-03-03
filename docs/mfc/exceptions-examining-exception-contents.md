---
title: "Özel durumlar: Özel durum içeriklerini İnceleme | Microsoft Docs"
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
- exception handling [MFC], MFC
- try-catch exception handling [MFC], MFC function exceptions
- catch blocks, MFC function exceptions
- CException class [MFC], class exceptions
- try-catch exception handling [MFC], exception contents
- throwing exceptions [MFC], exception contents
ms.assetid: dfda4782-b969-4f60-b867-cc204ea7f33a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 953dd61247f7d14ad04d5d5f85529c89f3aaad9d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="exceptions-examining-exception-contents"></a>Özel Durumlar: Özel Durum İçeriklerini İnceleme
Ancak bir **catch** bloğun bağımsız değişkeni, neredeyse her veri türü olabilir, MFC işlevleri sınıfından türetilen türlerin özel durumlar oluşturma `CException`. MFC işlevi tarafından oluşturulan bir özel yakalamak için daha sonra yazdığınız bir **catch** , bağımsız değişkeni bir işaretçidir bloğu için bir `CException` nesne (veya bir nesne türetilmiş `CException`, gibi `CMemoryException`). Özel durum tam türüne bağlı olarak, özel durumun belirli nedeni hakkında bilgi toplamak için özel durum nesnesi veri üyeleri inceleyebilirsiniz.  
  
 Örneğin, `CFileException` türüne sahip `m_cause` dosya özel durumu nedenini belirten bir numaralandırılmış türünü içeren veri üyesi. Bazı olası örnekler dönüş değerleri **CFileException::fileNotFound** ve **CFileException::readOnly**.  
  
 Aşağıdaki örnek, içeriğini incelemek gösterilmiştir bir `CFileException`. Diğer özel durum türleri benzer şekilde incelenebilir.  
  
 [!code-cpp[NVC_MFCExceptions#13](../mfc/codesnippet/cpp/exceptions-examining-exception-contents_1.cpp)]  
  
 Daha fazla bilgi için bkz: [özel durumlar: özel durumlarda nesneleri serbest bırakma](../mfc/exceptions-freeing-objects-in-exceptions.md) ve [özel durumlar: çalýþýrçalýþma yakalama ve silme özel durumları](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel Durum İşleme](../mfc/exception-handling-in-mfc.md)

