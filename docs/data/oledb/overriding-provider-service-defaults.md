---
title: Sağlayıcı hizmet varsayılanlarını geçersiz kılma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- service providers [OLE DB]
- OLE DB services [OLE DB], overriding defaults
ms.assetid: 08e366c0-74d8-463b-93a6-d58a8dc195f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5e54a44be0ad5b7b07311d102871e584770fc441
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42465178"
---
# <a name="overriding-provider-service-defaults"></a>Sağlayıcı Hizmet Varsayılanlarını Geçersiz Kılma
Sağlayıcının OLEDB_SERVICES için kayıt defteri değeri için varsayılan değer olarak döndürülen [DBPROP_INIT_OLEDBSERVICES](/previous-versions/windows/desktop/ms716898\(v=vs.85\)) başlatma özelliği veri kaynağı nesnesi.  
  
 Kayıt defteri girişi var olduğu sürece, sağlayıcının nesneleri toplanır ve kullanıcı için etkin hizmetler ayarlayarak sağlayıcının Varsayılanı geçersiz kılabilirsiniz `DBPROP_INIT_OLEDBSERVICES` başlatmadan önce özelliği. Etkinleştirmek ya da belirli bir hizmet devre dışı bırakmak için kullanıcının genellikle geçerli değerini alır `DBPROP_INIT_OLEDBSERVICES` özelliğini ayarlar veya etkin veya devre dışı belirli bir özellik için bit temizler ve özelliği sıfırlar. `DBPROP_INIT_OLEDBSERVICES` OLE DB veya ADO için geçirilen bağlantı dizesinde doğrudan ayarlanabilir veya `IDataInitialize::GetDatasource`. Tek başına hizmetlerinden etkinleştirmek/devre dışı karşılık gelen değerler aşağıdaki tabloda listelenmiştir.  
  
|Varsayılan hizmetler etkin|DBPROP_INIT_OLEDBSERVICES özellik değeri|Bağlantı dizesinde değeri|  
|------------------------------|------------------------------------------------|--------------------------------|  
|Tüm hizmetler (varsayılan)|`DBPROPVAL_OS_ENABLEALL`|"OLE DB hizmetleri = -1;"|  
|Havuzu hariç ve AutoEnlistment|`DBPROPVAL_OS_ENABLEALL &`<br /><br /> `~DBPROPVAL_OS_RESOURCEPOOLING &`<br /><br /> `~DBPROPVAL_OS_TXNENLISTMENT`|"OLE DB Hizmetleri -4; ="|  
|Tüm istemci imleci hariç|`DBPROPVAL_OS_ENABLEALL &`<br /><br /> `~DBPROPVAL_OS_CLIENTCURSOR`|"OLE DB Hizmetleri -5; ="|  
|Tümünü hariç, AutoEnlistment ve istemci imleci|`DBPROPVAL_OS_ENABLEALL &`<br /><br /> `~DBPROPVAL_OS_TXNENLISTMENT &`<br /><br /> `~DBPROPVAL_OS_CLIENTCURSOR`|"OLE DB hizmetleri -7; ="|  
|Hizmet yok|`~DBPROPVAL_OS_ENABLEALL`|"OLE DB hizmetleri = 0;"|  
  
 Sağlayıcı için kayıt defteri girdisi yok, bileşen yöneticilerinin sağlayıcının nesneleri toplama değil ve hizmet, kullanıcı tarafından açıkça istenen bile çağrılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak havuzu oluşturma](/previous-versions/windows/desktop/ms713655\(v=vs.85\))   
 [Kaynak havuzu tüketiciler kullanma](/previous-versions/windows/desktop/ms715907\(v=vs.85\))   
 [Nasıl sağlayıcıları etkili bir şekilde kaynak havuzu ile çalışma](/previous-versions/windows/desktop/ms714906\(v=vs.85\))   
 [OLE DB Hizmetlerini Etkinleştirme ve Devre Dışı Bırakma](../../data/oledb/enabling-and-disabling-ole-db-services.md)