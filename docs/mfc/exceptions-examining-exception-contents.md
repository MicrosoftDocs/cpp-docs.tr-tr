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
ms.openlocfilehash: 7500db2a29f9d4ccef37b9265f5f2968c2d07993
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217954"
---
# <a name="exceptions-examining-exception-contents"></a>Özel Durumlar: Özel Durum İçeriklerini İnceleme

Bir **`catch`** bloğun bağımsız değişkeni neredeyse herhangi bir veri türünde olabilir, ancak MFC işlevleri sınıfından türetilen türlerin özel durumlarını atar `CException` . Bir MFC işlevi tarafından oluşturulan bir özel durumu yakalamak için, **`catch`** bağımsız değişkeni bir `CException` nesne işaretçisi (veya gibi öğesinden türetilmiş bir nesne) olan bir blok yazarsınız `CException` `CMemoryException` . Özel durumun tam türüne bağlı olarak, özel durumun özel nedeni hakkında bilgi toplamak için özel durum nesnesinin veri üyelerini inceleyebilirsiniz.

Örneğin, türü, `CFileException` `m_cause` dosya özel durumunun nedenini belirten bir numaralandırılmış tür içeren veri üyesine sahiptir. Olası dönüş değerlerine bazı örnekler `CFileException::fileNotFound` ve ' dir `CFileException::readOnly` .

Aşağıdaki örnek, öğesinin içeriğini nasıl inceleneceğini gösterir `CFileException` . Diğer özel durum türleri benzer şekilde incelenebilir.

[!code-cpp[NVC_MFCExceptions#13](codesnippet/cpp/exceptions-examining-exception-contents_1.cpp)]

Daha fazla bilgi için bkz. özel durumlar: özel durumlarda [nesneleri boşaltma](exceptions-freeing-objects-in-exceptions.md) ve özel durumlar [: özel durumları yakalama ve silme](exceptions-catching-and-deleting-exceptions.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](exception-handling-in-mfc.md)
