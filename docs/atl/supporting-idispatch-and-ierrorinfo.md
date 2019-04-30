---
title: IDispatch ve IErrorInfo destekleme
ms.date: 11/04/2016
helpviewer_keywords:
- ISupportErrorInfoImpl method
- IErrorInfo class suppor in ATL
- IDispatchImpl class
- IDispatch class support in ATL
ms.assetid: 7db2220f-319d-4ce9-9382-d340019f14f7
ms.openlocfilehash: 2dcebd215ff5e1bdf72323323dfbaebd16fa3403
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64342033"
---
# <a name="supporting-idispatch-and-ierrorinfo"></a>IDispatch ve IErrorInfo destekleme

Şablon sınıfı kullanabileceğiniz [Idispatchımpl](../atl/reference/idispatchimpl-class.md) bir varsayılan uygulamasını sağlamak üzere `IDispatch Interface` nesneniz üzerinde herhangi bir ikili arabirimler kısmı.

Nesnenizin kullanıyorsa `IErrorInfo` hataları istemciye geri sonra nesnenizin desteklemelidir bildirmek için arabirimi `ISupportErrorInfo Interface` arabirimi. Şablon sınıfı [Isupporterrorınfoımpl](../atl/reference/isupporterrorinfoimpl-class.md) nesneniz üzerinde hatası veriyorsa tek bir arabirim yalnızca varsa, bu uygulama için kolay bir yol sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[ATL COM Nesnelerinin Temelleri](../atl/fundamentals-of-atl-com-objects.md)
