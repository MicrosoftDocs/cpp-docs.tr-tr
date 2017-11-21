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
ms.openlocfilehash: b6d34f0d0616ae3980d1132b1f70812fe273d275
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="supporting-idispatch-and-ierrorinfo"></a>IDispatch ve IErrorInfo destekleme
Şablon sınıfı kullanabilirsiniz [IDispatchImpl](../atl/reference/idispatchimpl-class.md) bir varsayılan uygulamasını sağlamak için `IDispatch Interface` çift arabirimlerden nesneniz üzerinde kısmı.  
  
 Nesnenizin kullanıyorsa `IErrorInfo` hataları istemciye geri sonra nesnenizin desteklemelidir bildirmek için arabirimi `ISupportErrorInfo Interface` arabirimi. Şablon sınıfı [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) nesnenizin hatalarda oluşturan tek bir arabirim yalnızca varsa, bu uygulama için kolay bir yol sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL COM nesneleri temelleri](../atl/fundamentals-of-atl-com-objects.md)

