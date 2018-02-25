---
title: "Sağlayıcı hizmet Varsayılanları geçersiz kılma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- service providers [OLE DB]
- OLE DB services [OLE DB], overriding defaults
ms.assetid: 08e366c0-74d8-463b-93a6-d58a8dc195f8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8788de8ad28dc3c746155f59dee3ba5bb763bcaa
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="overriding-provider-service-defaults"></a>Sağlayıcı Hizmet Varsayılanlarını Geçersiz Kılma
Sağlayıcının kayıt defteri değeri için **OLEDB_SERVICES** için varsayılan değer olarak döndürülür [DBPROP_INIT_OLEDBSERVICES](https://msdn.microsoft.com/en-us/library/ms716898.aspx) başlatma özelliği veri kaynağı nesnesi.  
  
 Kayıt defteri girdisi var olduğu sürece, sağlayıcının nesneleri toplanır ve sağlayıcının varsayılan ayarlayarak etkin hizmetler için kullanıcı ayarlarını geçersiz kılabilir **DBPROP_INIT_OLEDBSERVICES** başlatmadan önce özelliği. Etkinleştirmek veya belirli bir hizmet devre dışı bırakmak için kullanıcının genellikle geçerli değerini alır **DBPROP_INIT_OLEDBSERVICES** özelliği, ayarlar ya da etkin veya devre dışı belirli özellik bitini temizler ve özelliği sıfırlar. **DBPROP_INIT_OLEDBSERVICES** doğrudan OLE DB veya ADO için geçirilen bağlantı dizesini ayarlamak veya **IDataInitialize::GetDatasource**. Tek tek Hizmetleri etkinleştir/devre dışı bırakılacak karşılık gelen değerler aşağıdaki tabloda listelenmiştir.  
  
|Varsayılan hizmetler etkin|DBPROP_INIT_OLEDBSERVICES özellik değeri|Bağlantı dizesindeki değer|  
|------------------------------|------------------------------------------------|--------------------------------|  
|Tüm hizmetler (varsayılan)|**DBPROPVAL_OS_ENABLEALL**|"OLE DB hizmetleri = -1;"|  
|Hariç tüm ve AutoEnlistment|**DBPROPVAL_OS_ENABLEALL &**<br /><br /> **~ DBPROPVAL_OS_RESOURCEPOOLING &**<br /><br /> **~ DBPROPVAL_OS_TXNENLISTMENT**|"OLE DB Hizmetleri-; 4 ="|  
|Tüm istemci imleci hariç|**DBPROPVAL_OS_ENABLEALL** &<br /><br /> ~**DBPROPVAL_OS_CLIENTCURSOR**|"OLE DB Hizmetleri = -5;"|  
|Tüm hariç, AutoEnlistment ve istemci imleci|**DBPROPVAL_OS_ENABLEALL &**<br /><br /> **~ DBPROPVAL_OS_TXNENLISTMENT &**<br /><br /> **~DBPROPVAL_OS_CLIENTCURSOR**|"OLE DB Services = -7;"|  
|Hizmet yok|~**DBPROPVAL_OS_ENABLEALL**|"OLE DB Services = 0;"|  
  
 Kayıt defteri girdisini sağlayıcı için mevcut değilse, bileşen yöneticilerinin sağlayıcının nesnelerin araya değil ve hiçbir hizmet, kullanıcı tarafından açıkça istenmiş olsa bile çağrılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak havuzu oluşturma](https://msdn.microsoft.com/en-us/library/ms713655.aspx)   
 [Kaynak havuzu tüketiciler nasıl kullanır](https://msdn.microsoft.com/en-us/library/ms715907.aspx)   
 [Nasıl sağlayıcıları etkili bir şekilde kaynak havuzu ile çalışma](https://msdn.microsoft.com/en-us/library/ms714906.aspx)   
 [OLE DB Hizmetlerini Etkinleştirme ve Devre Dışı Bırakma](../../data/oledb/enabling-and-disabling-ole-db-services.md)