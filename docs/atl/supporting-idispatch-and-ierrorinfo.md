---
description: 'Hakkında daha fazla bilgi edinin: IDispatch ve IErrorInfo'
title: IDispatch ve IErrorInfo desteği
ms.date: 11/04/2016
helpviewer_keywords:
- ISupportErrorInfoImpl method
- IErrorInfo class suppor in ATL
- IDispatchImpl class
- IDispatch class support in ATL
ms.assetid: 7db2220f-319d-4ce9-9382-d340019f14f7
ms.openlocfilehash: 4622c8811fafc9512400345e5876dd24c466bc93
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138456"
---
# <a name="supporting-idispatch-and-ierrorinfo"></a>IDispatch ve IErrorInfo desteği

Nesnelerinizde herhangi bir çift arabirimin bölümünün varsayılan bir uygulamasını sağlamak için [IDispatchImpl](../atl/reference/idispatchimpl-class.md) şablon sınıfını kullanabilirsiniz `IDispatch Interface` .

Nesneniz `IErrorInfo` hataları istemciye geri bildirmek için arabirimini kullanıyorsa, nesnenizin arabirimini desteklemesi gerekir `ISupportErrorInfo Interface` . [Iımporterrorınfoımpl](../atl/reference/isupporterrorinfoimpl-class.md) şablon sınıfı, yalnızca nesneniz üzerinde hata üreten tek bir arabiriminiz varsa bunu uygulamak için kolay bir yol sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[ATL COM nesnelerinin temelleri](../atl/fundamentals-of-atl-com-objects.md)
