---
title: Veri Nesneleri ve Veri Kaynakları (OLE)
ms.date: 11/04/2016
helpviewer_keywords:
- data objects [MFC], definition
- data transfer [MFC]
- OLE [MFC], data transfer
- data sources [MFC], definition
- data transfer [MFC], definition
- OLE [MFC], data objects
- OLE [MFC], data sources
ms.assetid: 8f68eed8-0ce8-4489-a4cc-f95554f89090
ms.openlocfilehash: dfe400dddfecce3e52337f7f449e975dff2ca83e
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616216"
---
# <a name="data-objects-and-data-sources-ole"></a>Veri Nesneleri ve Veri Kaynakları (OLE)

Bir veri aktarımı gerçekleştirdiğinizde, pano veya sürükleyip bırakma aracılığıyla verilerin kaynağı ve hedefi vardır. Bir uygulama, verileri kopyalama için sağlar ve başka bir uygulama yapıştırmak için kabul eder. Aktarımın her tarafının, aktarımın başarılı olması için aynı verilerde farklı işlemler gerçekleştirmesi gerekir. Microsoft Foundation Class (MFC) kitaplığı, bu aktarmanın her tarafını temsil eden iki sınıf sağlar:

- Veri kaynakları (nesneler tarafından uygulanan şekilde `COleDataSource` ) veri aktarımının kaynak tarafını temsil eder. Veriler panoya kopyalandıklarında ya da bir sürükle ve bırak işlemi için veriler sağlandığında kaynak uygulama tarafından oluşturulur.

- Veri nesneleri (nesneler tarafından uygulanan şekilde `COleDataObject` ) veri aktarımının hedef tarafını temsil eder. Bunlar, hedef uygulamada kendisine veri bırakıldığında veya Panodan bir yapıştırma işlemi gerçekleştirmesi istendiğinde oluşturulur.

Aşağıdaki makalelerde, uygulamalarınızda veri nesnelerinin ve veri kaynaklarının nasıl kullanılacağı açıklanmaktadır. Bu bilgiler hem kapsayıcı hem de sunucu uygulamaları için geçerlidir, çünkü verileri kopyalamak ve yapıştırmak için her ikisi de çağrılabilir.

- [Veri Nesneleri ve Veri Kaynakları: Oluşturma ve Yok Etme](data-objects-and-data-sources-creation-and-destruction.md)

- [Veri Nesneleri ve Veri Kaynakları: Düzenleme](data-objects-and-data-sources-manipulation.md)

## <a name="in-this-section"></a>Bu Bölümde

[Sürükleme ve Bırakma](drag-and-drop-ole.md)

[Pano](clipboard.md)

## <a name="see-also"></a>Ayrıca bkz.

[OLE](ole-in-mfc.md)<br/>
[Cotadataobject sınıfı](reference/coledataobject-class.md)<br/>
[Cotadatasource sınıfı](reference/coledatasource-class.md)
