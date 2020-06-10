---
title: Ağaç Denetimi ile İletişim
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], communicating with
- CTreeCtrl class [MFC], calling member functions
- communications, tree controls
- tree controls
ms.assetid: 680ad9ee-b11f-452d-93fa-501ca7d7e069
ms.openlocfilehash: f480cdad2fce53f830b8067083a8a4be4b4e4848
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619655"
---
# <a name="communicating-with-a-tree-control"></a>Ağaç Denetimi ile İletişim

Nesnenin oluşturulma şekline bağlı olarak bir [Ctreeci](reference/ctreectrl-class.md) nesnesinde üye işlevleri çağırmak için farklı yöntemler kullanırsınız:

- Ağaç denetimi bir iletişim kutusunda ise, `CTreeCtrl` iletişim kutusu sınıfında oluşturduğunuz türünde bir üye değişkeni kullanın.

- Ağaç denetimi bir alt pencere ise, `CTreeCtrl` nesneyi oluşturmak için kullandığınız nesneyi (veya işaretçiyi) kullanın.

- Bir `CTreeView` nesnesi kullanıyorsanız, ağaç denetimine bir başvuru almak Için [CTreeView:: Gettreecini](reference/ctreeview-class.md#gettreectrl) işlevini kullanın. Bu değerle başka bir başvuru başlatabilir veya başvurunun adresini bir `CTreeCtrl` işaretçiye atayabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[CTreeCtrl Kullanma](using-ctreectrl.md)<br/>
[Denetimler](controls-mfc.md)
