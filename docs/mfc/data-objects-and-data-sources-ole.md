---
description: 'Daha fazla bilgi edinin: veri nesneleri ve veri kaynakları (OLE)'
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
ms.openlocfilehash: 719053e2a75b18fbf54440403351198acc66b9d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291213"
---
# <a name="data-objects-and-data-sources-ole"></a>Veri Nesneleri ve Veri Kaynakları (OLE)

Bir veri aktarımı gerçekleştirdiğinizde, pano veya sürükleyip bırakma aracılığıyla verilerin kaynağı ve hedefi vardır. Bir uygulama, verileri kopyalama için sağlar ve başka bir uygulama yapıştırmak için kabul eder. Aktarımın her tarafının, aktarımın başarılı olması için aynı verilerde farklı işlemler gerçekleştirmesi gerekir. Microsoft Foundation Class (MFC) kitaplığı, bu aktarmanın her tarafını temsil eden iki sınıf sağlar:

- Veri kaynakları (nesneler tarafından uygulanan şekilde `COleDataSource` ) veri aktarımının kaynak tarafını temsil eder. Veriler panoya kopyalandıklarında ya da bir sürükle ve bırak işlemi için veriler sağlandığında kaynak uygulama tarafından oluşturulur.

- Veri nesneleri (nesneler tarafından uygulanan şekilde `COleDataObject` ) veri aktarımının hedef tarafını temsil eder. Bunlar, hedef uygulamada kendisine veri bırakıldığında veya Panodan bir yapıştırma işlemi gerçekleştirmesi istendiğinde oluşturulur.

Aşağıdaki makalelerde, uygulamalarınızda veri nesnelerinin ve veri kaynaklarının nasıl kullanılacağı açıklanmaktadır. Bu bilgiler hem kapsayıcı hem de sunucu uygulamaları için geçerlidir, çünkü verileri kopyalamak ve yapıştırmak için her ikisi de çağrılabilir.

- [Veri nesneleri ve veri kaynakları: oluşturma ve yok etme](data-objects-and-data-sources-creation-and-destruction.md)

- [Veri nesneleri ve veri kaynakları: düzenleme](data-objects-and-data-sources-manipulation.md)

## <a name="in-this-section"></a>Bu Bölümde

[Sürükleme ve Bırakma](drag-and-drop-ole.md)

[Pano](clipboard.md)

## <a name="see-also"></a>Ayrıca bkz.

[OLE](ole-in-mfc.md)<br/>
[Cotadataobject sınıfı](reference/coledataobject-class.md)<br/>
[Cotadatasource sınıfı](reference/coledatasource-class.md)
