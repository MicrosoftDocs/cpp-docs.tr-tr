---
title: IDispatch ve IErrorInfo destekleyen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IErrorInfo
- IDispatch
dev_langs: C++
helpviewer_keywords:
- ISupportErrorInfoImpl method
- IErrorInfo class suppor in ATL
- IDispatchImpl class
- IDispatch class support in ATL
ms.assetid: 7db2220f-319d-4ce9-9382-d340019f14f7
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f39db3e844df884e8e95352bed2a078b01beede8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="supporting-idispatch-and-ierrorinfo"></a>IDispatch ve IErrorInfo destekleme
Şablon sınıfı kullanabilirsiniz [IDispatchImpl](../atl/reference/idispatchimpl-class.md) bir varsayılan uygulamasını sağlamak için `IDispatch Interface` çift arabirimlerden nesneniz üzerinde kısmı.  
  
 Nesnenizin kullanıyorsa `IErrorInfo` hataları istemciye geri sonra nesnenizin desteklemelidir bildirmek için arabirimi `ISupportErrorInfo Interface` arabirimi. Şablon sınıfı [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) nesnenizin hatalarda oluşturan tek bir arabirim yalnızca varsa, bu uygulama için kolay bir yol sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL COM Nesnelerinin Temelleri](../atl/fundamentals-of-atl-com-objects.md)

