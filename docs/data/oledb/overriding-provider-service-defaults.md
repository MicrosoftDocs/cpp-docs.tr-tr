---
title: Sağlayıcı Hizmet Varsayılanlarını Geçersiz Kılma
ms.date: 10/29/2018
helpviewer_keywords:
- service providers [OLE DB]
- OLE DB services [OLE DB], overriding defaults
ms.assetid: 08e366c0-74d8-463b-93a6-d58a8dc195f8
ms.openlocfilehash: 4cf3ad1064627f64315822a5045642aa50330d10
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209820"
---
# <a name="overriding-provider-service-defaults"></a>Sağlayıcı Hizmet Varsayılanlarını Geçersiz Kılma

OLEDB_SERVICES için sağlayıcının kayıt defteri değeri, veri kaynağı nesnesindeki [DBPROP_INIT_OLEDBSERVICES](/previous-versions/windows/desktop/ms716898(v=vs.85)) başlatma özelliği için varsayılan değer olarak döndürülür.

Kayıt defteri girdisi mevcut olduğu sürece, sağlayıcının nesneleri toplanır. Kullanıcı, başlatma öncesinde DBPROP_INIT_OLEDBSERVICES özelliğini ayarlayarak, etkin hizmetler için sağlayıcının varsayılan ayarını geçersiz kılabilir. Belirli bir hizmeti etkinleştirmek veya devre dışı bırakmak için Kullanıcı DBPROP_INIT_OLEDBSERVICES özelliğinin geçerli değerini alır, etkin veya devre dışı olarak belirli bir özelliğin bitini ayarlar veya temizler ve özelliği sıfırlar. DBPROP_INIT_OLEDBSERVICES doğrudan OLE DB veya ADO veya `IDataInitialize::GetDatasource`iletilen bağlantı dizesinde ayarlanabilir. Ayrı hizmetleri etkinleştirmek/devre dışı bırakmak için karşılık gelen değerler aşağıdaki tabloda listelenmiştir.

|Varsayılan hizmetler etkin|DBPROP_INIT_OLEDBSERVICES Özellik değeri|Bağlantı dizesindeki değer|
|------------------------------|------------------------------------------------|--------------------------------|
|Tüm hizmetler (varsayılan)|DBPROPVAL_OS_ENABLEALL|"OLE DB hizmetleri =-1;"|
|Havuz ve oto kaydı dışında tümü|`DBPROPVAL_OS_ENABLEALL &`<br /><br /> `~DBPROPVAL_OS_RESOURCEPOOLING &`<br /><br /> `~DBPROPVAL_OS_TXNENLISTMENT`|"OLE DB Hizmetleri =-4;"|
|Istemci Imleci hariç tümü|`DBPROPVAL_OS_ENABLEALL &`<br /><br /> `~DBPROPVAL_OS_CLIENTCURSOR`|"OLE DB Hizmetleri =-5;"|
|Havuz, oto kaydı ve Istemci Imleci hariç tümü|`DBPROPVAL_OS_ENABLEALL &`<br /><br /> `~DBPROPVAL_OS_TXNENLISTMENT &`<br /><br /> `~DBPROPVAL_OS_CLIENTCURSOR`|"OLE DB hizmetleri =-7;"|
|Hizmet yok|`~DBPROPVAL_OS_ENABLEALL`|"OLE DB hizmetleri = 0;"|

Sağlayıcı için kayıt defteri girişi yoksa, bileşen yöneticileri sağlayıcının nesnelerini toplamaz. Kullanıcı tarafından açıkça istenmiş olsa bile hiçbir hizmet açık olmayacaktır.

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak havuzu oluşturma](/previous-versions/windows/desktop/ms713655(v=vs.85))<br/>
[Tüketiciler kaynak havuzunu nasıl kullanır?](/previous-versions/windows/desktop/ms715907(v=vs.85))<br/>
[Sağlayıcılar kaynak havuzuyla etkin bir şekilde nasıl çalışır?](/previous-versions/windows/desktop/ms714906(v=vs.85))<br/>
[OLE DB Hizmetlerini Etkinleştirme ve Devre Dışı Bırakma](../../data/oledb/enabling-and-disabling-ole-db-services.md)<br/>
