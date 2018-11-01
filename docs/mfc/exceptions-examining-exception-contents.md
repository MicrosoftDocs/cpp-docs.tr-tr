---
title: 'Özel Durumlar: Özel Durum İçeriklerini İnceleme'
ms.date: 11/04/2016
helpviewer_keywords:
- exception handling [MFC], MFC
- try-catch exception handling [MFC], MFC function exceptions
- catch blocks, MFC function exceptions
- CException class [MFC], class exceptions
- try-catch exception handling [MFC], exception contents
- throwing exceptions [MFC], exception contents
ms.assetid: dfda4782-b969-4f60-b867-cc204ea7f33a
ms.openlocfilehash: 4355a575f29741d0c7b9f1e12e40ca9d977219b8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630085"
---
# <a name="exceptions-examining-exception-contents"></a>Özel Durumlar: Özel Durum İçeriklerini İnceleme

Ancak bir **catch** bloğun bağımsız değişkeni, neredeyse her veri türü olabilir, özel durum sınıfından türetilen türlerin MFC işlevleri throw `CException`. Bir MFC işlevi tarafından oluşturulan bir özel durum yakalamak için ardından yazdığınız bir **catch** , bağımsız değişken bir işaretçidir bloğu için bir `CException` nesnesi (veya bir nesne öğesinden türetilen `CException`, gibi `CMemoryException`). Özel durumun tam türüne bağlı olarak, özel durumun belirli nedeni hakkında bilgi toplamak için özel durum nesnesi veri üyeleri inceleyebilirsiniz.

Örneğin, `CFileException` türünde `m_cause` dosya özel durumun nedenini belirten bir listeden seçimli türü içeren veri üyesi. Bazı olası örnekler dönüş değerleri `CFileException::fileNotFound` ve `CFileException::readOnly`.

Aşağıdaki örnek, içeriğini incelemek gösterilmiştir bir `CFileException`. Diğer özel durum türlerine benzer şekilde incelenebilir.

[!code-cpp[NVC_MFCExceptions#13](../mfc/codesnippet/cpp/exceptions-examining-exception-contents_1.cpp)]

Daha fazla bilgi için [özel durumlar: özel durumlarda nesneleri serbest bırakma](../mfc/exceptions-freeing-objects-in-exceptions.md) ve [özel durumlar: çalýþýrçalýþma yakalama ve silme özel durumları](../mfc/exceptions-catching-and-deleting-exceptions.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Özel Durum İşleme](../mfc/exception-handling-in-mfc.md)

