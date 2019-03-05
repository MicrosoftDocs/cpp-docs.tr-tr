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
ms.openlocfilehash: aa3800b529238ba78cb3aacc555d1a1d7afb94ca
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57290553"
---
# <a name="supporting-idispatch-and-ierrorinfo"></a>IDispatch ve IErrorInfo destekleme

Şablon sınıfı kullanabileceğiniz [Idispatchımpl](../atl/reference/idispatchimpl-class.md) bir varsayılan uygulamasını sağlamak üzere `IDispatch Interface` nesneniz üzerinde herhangi bir ikili arabirimler kısmı.

Nesnenizin kullanıyorsa `IErrorInfo` hataları istemciye geri sonra nesnenizin desteklemelidir bildirmek için arabirimi `ISupportErrorInfo Interface` arabirimi. Şablon sınıfı [Isupporterrorınfoımpl](../atl/reference/isupporterrorinfoimpl-class.md) nesneniz üzerinde hatası veriyorsa tek bir arabirim yalnızca varsa, bu uygulama için kolay bir yol sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[ATL COM Nesnelerinin Temelleri](../atl/fundamentals-of-atl-com-objects.md)
