---
title: OLE ile ilgili sınıflar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.ole
dev_langs:
- C++
helpviewer_keywords:
- ActiveX classes [MFC]
- OLE classes [MFC]
- OLE [MFC], classes
ms.assetid: 2135cf54-1d9d-4e0e-91b4-943b3440effa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f43dadaa4aaefa677106710d1adbcdf0e60be59d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46411319"
---
# <a name="ole-related-classes"></a>OLE İle İlgili Sınıflar

Bu sınıflar, bir dizi girdi ve çıktı dosya için özel durumlar arasında değişen farklı hizmet sunar.

[COleObjectFactory](../mfc/reference/coleobjectfactory-class.md)<br/>
Diğer kapsayıcılardan istendiğinde öğeleri oluşturmak için kullanılır. Bu sınıf fabrikaları dahil olmak üzere, daha özel türleri için temel sınıf olarak hizmet veren `COleTemplateServer`.

[COleMessageFilter](../mfc/reference/colemessagefilter-class.md)<br/>
Eşzamanlılık ile OLE basit uzak yordam çağrıları (LRPC) yönetmek için kullanılır.

[COleStreamFile](../mfc/reference/colestreamfile-class.md)<br/>
COM kullanan `IStream` sağlamak için arabirimi `CFile` bileşik dosyalar için erişim. Bu sınıf (türetilen `CFile`) OLE yapılandırılmış depolama kullanmak MFC serileştirme sağlar.

[CRectTracker](../mfc/reference/crecttracker-class.md)<br/>
Taşıma, yeniden boyutlandırma ve yerinde öğelerinin reorientation sağlamak için kullanılır.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../mfc/class-library-overview.md)

