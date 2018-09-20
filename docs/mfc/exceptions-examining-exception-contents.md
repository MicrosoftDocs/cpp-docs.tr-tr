---
title: 'Özel durumlar: Özel durum içeriklerini İnceleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f5fb0df0c16e9aea2f334b6c08f92a3bef4ea486
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378392"
---
# <a name="exceptions-examining-exception-contents"></a>Özel Durumlar: Özel Durum İçeriklerini İnceleme

Ancak bir **catch** bloğun bağımsız değişkeni, neredeyse her veri türü olabilir, özel durum sınıfından türetilen türlerin MFC işlevleri throw `CException`. Bir MFC işlevi tarafından oluşturulan bir özel durum yakalamak için ardından yazdığınız bir **catch** , bağımsız değişken bir işaretçidir bloğu için bir `CException` nesnesi (veya bir nesne öğesinden türetilen `CException`, gibi `CMemoryException`). Özel durumun tam türüne bağlı olarak, özel durumun belirli nedeni hakkında bilgi toplamak için özel durum nesnesi veri üyeleri inceleyebilirsiniz.

Örneğin, `CFileException` türünde `m_cause` dosya özel durumun nedenini belirten bir listeden seçimli türü içeren veri üyesi. Bazı olası örnekler dönüş değerleri `CFileException::fileNotFound` ve `CFileException::readOnly`.

Aşağıdaki örnek, içeriğini incelemek gösterilmiştir bir `CFileException`. Diğer özel durum türlerine benzer şekilde incelenebilir.

[!code-cpp[NVC_MFCExceptions#13](../mfc/codesnippet/cpp/exceptions-examining-exception-contents_1.cpp)]

Daha fazla bilgi için [özel durumlar: özel durumlarda nesneleri serbest bırakma](../mfc/exceptions-freeing-objects-in-exceptions.md) ve [özel durumlar: çalýþýrçalýþma yakalama ve silme özel durumları](../mfc/exceptions-catching-and-deleting-exceptions.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Özel Durum İşleme](../mfc/exception-handling-in-mfc.md)

