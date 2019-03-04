---
title: 'Özel durumlar: Özel durum içeriklerini İnceleme'
ms.date: 11/04/2016
helpviewer_keywords:
- exception handling [MFC], MFC
- try-catch exception handling [MFC], MFC function exceptions
- catch blocks, MFC function exceptions
- CException class [MFC], class exceptions
- try-catch exception handling [MFC], exception contents
- throwing exceptions [MFC], exception contents
ms.assetid: dfda4782-b969-4f60-b867-cc204ea7f33a
ms.openlocfilehash: f6f9bca6f6b7ca9d104cb492c760ab89f7163afd
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57259392"
---
# <a name="exceptions-examining-exception-contents"></a>Özel durumlar: Özel durum içeriklerini İnceleme

Ancak bir **catch** bloğun bağımsız değişkeni, neredeyse her veri türü olabilir, özel durum sınıfından türetilen türlerin MFC işlevleri throw `CException`. Bir MFC işlevi tarafından oluşturulan bir özel durum yakalamak için ardından yazdığınız bir **catch** , bağımsız değişken bir işaretçidir bloğu için bir `CException` nesnesi (veya bir nesne öğesinden türetilen `CException`, gibi `CMemoryException`). Özel durumun tam türüne bağlı olarak, özel durumun belirli nedeni hakkında bilgi toplamak için özel durum nesnesi veri üyeleri inceleyebilirsiniz.

Örneğin, `CFileException` türünde `m_cause` dosya özel durumun nedenini belirten bir listeden seçimli türü içeren veri üyesi. Bazı olası örnekler dönüş değerleri `CFileException::fileNotFound` ve `CFileException::readOnly`.

Aşağıdaki örnek, içeriğini incelemek gösterilmiştir bir `CFileException`. Diğer özel durum türlerine benzer şekilde incelenebilir.

[!code-cpp[NVC_MFCExceptions#13](../mfc/codesnippet/cpp/exceptions-examining-exception-contents_1.cpp)]

Daha fazla bilgi için [özel durumlar: Özel durumlarda nesneleri serbest bırakma](../mfc/exceptions-freeing-objects-in-exceptions.md) ve [özel durumlar: Yakalama ve özel durumları silme](../mfc/exceptions-catching-and-deleting-exceptions.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](../mfc/exception-handling-in-mfc.md)
