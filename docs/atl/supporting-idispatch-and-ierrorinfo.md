---
title: IDispatch ve IErrorInfo destekleme
ms.date: 11/04/2016
f1_keywords:
- IErrorInfo
- IDispatch
helpviewer_keywords:
- ISupportErrorInfoImpl method
- IErrorInfo class suppor in ATL
- IDispatchImpl class
- IDispatch class support in ATL
ms.assetid: 7db2220f-319d-4ce9-9382-d340019f14f7
ms.openlocfilehash: ea45f0bdd2363f4392baee049629c55259e45af0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50502442"
---
# <a name="supporting-idispatch-and-ierrorinfo"></a>IDispatch ve IErrorInfo destekleme

Şablon sınıfı kullanabileceğiniz [Idispatchımpl](../atl/reference/idispatchimpl-class.md) bir varsayılan uygulamasını sağlamak üzere `IDispatch Interface` nesneniz üzerinde herhangi bir ikili arabirimler kısmı.

Nesnenizin kullanıyorsa `IErrorInfo` hataları istemciye geri sonra nesnenizin desteklemelidir bildirmek için arabirimi `ISupportErrorInfo Interface` arabirimi. Şablon sınıfı [Isupporterrorınfoımpl](../atl/reference/isupporterrorinfoimpl-class.md) nesneniz üzerinde hatası veriyorsa tek bir arabirim yalnızca varsa, bu uygulama için kolay bir yol sağlar.

## <a name="see-also"></a>Ayrıca Bkz.

[ATL COM Nesnelerinin Temelleri](../atl/fundamentals-of-atl-com-objects.md)

