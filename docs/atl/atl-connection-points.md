---
title: ATL bağlantı noktaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- connections, connection points
- ATL, connection points
- connection points [C++], about connection points
ms.assetid: 17d76165-5f83-4f95-b36d-483821c247a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 179f4329d55261d71d3d122e6a2601ce7e805c0f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="atl-connection-points"></a>ATL Bağlantı Noktaları
Bir bağlanılabilirlik giden arabirimleri destekleyen bir nesnedir. İstemcisi ile iletişim kurmak için nesne giden bir arabirim sağlar. Giden her arabirim için bir bağlantı noktası bağlanılabilirlik nesne kullanıma sunar. Her giden arabirimi bir havuz adlı bir nesne üzerinde bir istemci tarafından uygulanır.  
  
 ![Bağlantı noktaları](../atl/media/vc2zw31.gif "vc2zw31")  
  
 Her bağlantı noktası destekleyen [IConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms694318) arabirimi. Kendi bağlantı noktaları aracılığıyla istemcisine bağlanılabilirlik nesneyi kullanıma sunan [IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857) arabirimi.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [ATL Bağlantı Noktası Sınıfları](../atl/atl-connection-point-classes.md)  
 Bağlantı noktaları destek ATL sınıfları kısaca açıklanmaktadır.  
  
 [Bir Nesneye Bağlantı Noktaları Ekleme](../atl/adding-connection-points-to-an-object.md)  
 Bağlantı noktaları için bir nesne eklemek için kullanılan adımlar açıklanır.  
  
 [ATL Bağlantı Noktası Örneği](../atl/atl-connection-point-example.md)  
 Bir bağlantı noktası bildirme ilişkin bir örnek verilmektedir.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Etkin Şablon Kütüphanesi kullanarak programı kavramsal konulara bağlantılar verilmektedir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../atl/active-template-library-atl-concepts.md)

