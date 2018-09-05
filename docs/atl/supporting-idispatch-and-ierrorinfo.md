---
title: IDispatch ve IErrorInfo destekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- IErrorInfo
- IDispatch
dev_langs:
- C++
helpviewer_keywords:
- ISupportErrorInfoImpl method
- IErrorInfo class suppor in ATL
- IDispatchImpl class
- IDispatch class support in ATL
ms.assetid: 7db2220f-319d-4ce9-9382-d340019f14f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0d9c27dfe81c3bbd2978f418c8e942ac20190b30
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43753614"
---
# <a name="supporting-idispatch-and-ierrorinfo"></a>IDispatch ve IErrorInfo destekleme

Şablon sınıfı kullanabileceğiniz [Idispatchımpl](../atl/reference/idispatchimpl-class.md) bir varsayılan uygulamasını sağlamak üzere `IDispatch Interface` nesneniz üzerinde herhangi bir ikili arabirimler kısmı.

Nesnenizin kullanıyorsa `IErrorInfo` hataları istemciye geri sonra nesnenizin desteklemelidir bildirmek için arabirimi `ISupportErrorInfo Interface` arabirimi. Şablon sınıfı [Isupporterrorınfoımpl](../atl/reference/isupporterrorinfoimpl-class.md) nesneniz üzerinde hatası veriyorsa tek bir arabirim yalnızca varsa, bu uygulama için kolay bir yol sağlar.

## <a name="see-also"></a>Ayrıca Bkz.

[ATL COM Nesnelerinin Temelleri](../atl/fundamentals-of-atl-com-objects.md)

