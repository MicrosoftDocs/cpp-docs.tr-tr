---
title: OLE İle İlgili Sınıflar
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX classes [MFC]
- OLE classes [MFC]
- OLE [MFC], classes
ms.assetid: 2135cf54-1d9d-4e0e-91b4-943b3440effa
ms.openlocfilehash: 6f6db6ce133b440a5ed86e7c1642396888744540
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621028"
---
# <a name="ole-related-classes"></a>OLE İle İlgili Sınıflar

Bu sınıflar, özel durumlardan dosya girişi ve çıkışı arasında değişen farklı hizmetler sunar.

[COleObjectFactory](reference/coleobjectfactory-class.md)<br/>
Diğer kapsayıcılardan istendiğinde öğe oluşturmak için kullanılır. Bu sınıf, dahil olmak üzere daha belirli fabrika türleri için temel sınıf olarak hizmet verir `COleTemplateServer` .

[Cotamessagefilter](reference/colemessagefilter-class.md)<br/>
OLE basit uzak yordam çağrıları (LRPC) ile eşzamanlılığı yönetmek için kullanılır.

[Cotastreamfile](reference/colestreamfile-class.md)<br/>
`IStream`Bileşik dosyalara erişim sağlamak IÇIN com arabirimini kullanır `CFile` . Bu sınıf (öğesinden türetilmiş `CFile` ), MFC serileştirmesini OLE yapılandırılmış depolamayı kullanacak şekilde sağlar.

[CRectTracker](reference/crecttracker-class.md)<br/>
Yerinde öğelerin taşınması, yeniden boyutlandırılması ve yeniden yönlendirmesine izin vermek için kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](class-library-overview.md)
