---
title: Sağlayıcı Hizmet Varsayılanlarını Geçersiz Kılma
ms.date: 10/29/2018
helpviewer_keywords:
- service providers [OLE DB]
- OLE DB services [OLE DB], overriding defaults
ms.assetid: 08e366c0-74d8-463b-93a6-d58a8dc195f8
ms.openlocfilehash: 9f845834b844c16bf2820a295768696e8f6a6526
ms.sourcegitcommit: c40469825b6101baac87d43e5f4aed6df6b078f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/12/2018
ms.locfileid: "51556302"
---
# <a name="overriding-provider-service-defaults"></a>Sağlayıcı Hizmet Varsayılanlarını Geçersiz Kılma

Sağlayıcının OLEDB_SERVICES için kayıt defteri değeri için varsayılan değer olarak döndürülen [DBPROP_INIT_OLEDBSERVICES](https://docs.microsoft.com/previous-versions/windows/desktop/ms716898(v=vs.85)) başlatma özelliği veri kaynağı nesnesi.

Kayıt defteri girişi var olduğu sürece, sağlayıcının nesneleri toplanır. Kullanıcı etkin hizmetler için önce DBPROP_INIT_OLEDBSERVICES özelliği ayarlayarak sağlayıcının Varsayılanı geçersiz kılabilirsiniz. Etkinleştirmek veya devre dışı belirli bir hizmet için kullanıcı DBPROP_INIT_OLEDBSERVICES özelliğinin geçerli değeri alır, ayarlar veya etkin veya devre dışı belirli bir özellik için bit temizler ve özelliği sıfırlar. OLE DB veya ADO için geçirilen bağlantı dizesinde doğrudan DBPROP_INIT_OLEDBSERVICES ayarlanabilir veya `IDataInitialize::GetDatasource`. Tek başına hizmetlerinden etkinleştirmek/devre dışı karşılık gelen değerler aşağıdaki tabloda listelenmiştir.

|Varsayılan hizmetler etkin|DBPROP_INIT_OLEDBSERVICES özellik değeri|Bağlantı dizesinde değeri|
|------------------------------|------------------------------------------------|--------------------------------|
|Tüm hizmetler (varsayılan)|DBPROPVAL_OS_ENABLEALL|"OLE DB hizmetleri = -1;"|
|Havuzu hariç ve AutoEnlistment|`DBPROPVAL_OS_ENABLEALL &`<br /><br /> `~DBPROPVAL_OS_RESOURCEPOOLING &`<br /><br /> `~DBPROPVAL_OS_TXNENLISTMENT`|"OLE DB Hizmetleri -4; ="|
|Tüm istemci imleci hariç|`DBPROPVAL_OS_ENABLEALL &`<br /><br /> `~DBPROPVAL_OS_CLIENTCURSOR`|"OLE DB Hizmetleri -5; ="|
|Tümünü hariç, AutoEnlistment ve istemci imleci|`DBPROPVAL_OS_ENABLEALL &`<br /><br /> `~DBPROPVAL_OS_TXNENLISTMENT &`<br /><br /> `~DBPROPVAL_OS_CLIENTCURSOR`|"OLE DB hizmetleri -7; ="|
|Hizmet yok|`~DBPROPVAL_OS_ENABLEALL`|"OLE DB hizmetleri = 0;"|

Sağlayıcı için kayıt defteri girdisi yok, bileşen yöneticilerinin sağlayıcının nesneleri toplamaz. Hizmet, kullanıcı tarafından açıkça istenen bile açılır.

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak havuzu oluşturma](https://docs.microsoft.com/previous-versions/windows/desktop/ms713655(v=vs.85))<br/>
[Kaynak havuzu tüketiciler kullanma](https://docs.microsoft.com/previous-versions/windows/desktop/ms715907(v=vs.85))<br/>
[Nasıl sağlayıcıları etkili bir şekilde kaynak havuzu ile çalışma](https://docs.microsoft.com/previous-versions/windows/desktop/ms714906(v=vs.85))<br/>
[OLE DB Hizmetlerini Etkinleştirme ve Devre Dışı Bırakma](../../data/oledb/enabling-and-disabling-ole-db-services.md)<br/>