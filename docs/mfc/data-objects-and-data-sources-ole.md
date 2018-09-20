---
title: Veri nesneleri ve veri kaynakları (OLE) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- data objects [MFC], definition
- data transfer [MFC]
- OLE [MFC], data transfer
- data sources [MFC], definition
- data transfer [MFC], definition
- OLE [MFC], data objects
- OLE [MFC], data sources
ms.assetid: 8f68eed8-0ce8-4489-a4cc-f95554f89090
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f933a8eb75c25921c3025f8ca1bc03a2c72fc81b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46443949"
---
# <a name="data-objects-and-data-sources-ole"></a>Veri Nesneleri ve Veri Kaynakları (OLE)

Veri aktarımı, Pano veya sürükle ve bırak kullanılarak gerçekleştirirken verileri kaynak ve hedef vardır. Kopyalamak için bir uygulama veri sağlar ve başka bir uygulamaya yapıştırma için bunu kabul eder. Aynı veri aktarımı başarılı olması için farklı işlemleri gerçekleştirmek her iki tarafındaki aktarım gerekir. Microsoft Foundation Class (MFC) kitaplığı, bu aktarımı her iki tarafındaki temsil eden iki sınıfları sağlar:

- Veri kaynakları (tarafından uygulanan `COleDataSource` nesneleri) veri aktarımı kaynak tarafı temsil eder. Veriler panoya kopyalanmak üzere olduğunda veya bir Sürükle ve bırak işlemi için veri sağlanmadığında bunlar kaynak uygulama tarafından oluşturulur.

- Veri nesneleri (tarafından uygulanan `COleDataObject` nesneleri) veri aktarımı hedef tarafı temsil eder. Hedef uygulama içine veya panodan yapıştırma işlemi gerçekleştirmek için sorulduğunda bırakılan veri sahip olduğunda oluşturulur.

Aşağıdaki makaleler veri nesneleri ve veri kaynakları, uygulamalarınızda nasıl kullanılacağını açıklar. Bu bilgiler, hem de bağlı verileri kopyalama ve yapıştırma için çağrılabilir çünkü kapsayıcı hem de sunucu uygulamaları için geçerlidir.

- [Veri Nesneleri ve Veri Kaynakları: Oluşturma ve Yok Etme](../mfc/data-objects-and-data-sources-creation-and-destruction.md)

- [Veri Nesneleri ve Veri Kaynakları: Düzenleme](../mfc/data-objects-and-data-sources-manipulation.md)

## <a name="in-this-section"></a>Bu Bölümde

[Sürükleme ve Bırakma](../mfc/drag-and-drop-ole.md)

[Pano](../mfc/clipboard.md)

## <a name="see-also"></a>Ayrıca Bkz.

[OLE](../mfc/ole-in-mfc.md)<br/>
[COleDataObject Sınıfı](../mfc/reference/coledataobject-class.md)<br/>
[COleDataSource Sınıfı](../mfc/reference/coledatasource-class.md)
