---
title: IUnknown
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IUnknown
helpviewer_keywords:
- COM interfaces, base interface
- IUnknown interface
ms.assetid: e6b85472-e54b-4b8c-b19f-4454d6c05a8f
ms.openlocfilehash: 047e109e8098ed89ac89c05e434b54c91fda189a
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57270587"
---
# <a name="iunknown"></a>IUnknown

[IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) diğer her COM arayüzünün temel arabirimdir.  Bu arabirim üç yöntemi tanımlar: [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)), [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref), ve [yayın](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release). [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) bir arabirim kullanıcısının nesnenin arabirimlerinin başka birine işaretçi soran sağlar. [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref) ve [yayın](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release) arabirimde sayılan başvuruyu uygular.

## <a name="see-also"></a>Ayrıca bkz.

[COM’a Giriş](../atl/introduction-to-com.md)<br/>
[IUnknown ve arabirimi devralma](/windows/desktop/com/iunknown-and-interface-inheritance)
