---
title: Oturum Nesnesi Arabirimleri
ms.date: 11/19/2018
helpviewer_keywords:
- session objects [OLE DB]
- session objects [OLE DB], interfaces
- OLE DB provider templates, object interfaces
- interfaces, session object
- interfaces, list of
ms.assetid: ac01a958-6dde-4bd7-8b63-94459e488335
ms.openlocfilehash: 284f93d96b974a616e957a65ef0c8aa39b33a564
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52176906"
---
# <a name="session-object-interfaces"></a>Oturum Nesnesi Arabirimleri

Aşağıdaki tabloda, bir oturum nesnesi için OLE DB tarafından tanımlanan zorunlu ve isteğe bağlı arabirimler gösterilir.

|Arabirim|Gerekli mi?|OLE DB Şablonları tarafından uygulanır?|
|---------------|---------------|--------------------------------------|
|[IGetDataSource](https://docs.microsoft.com/previous-versions/windows/desktop/ms709721(v=vs.85))|Zorunlu|Evet|
|[IOpenRowset](https://docs.microsoft.com/previous-versions/windows/desktop/ms716946(v=vs.85))|Zorunlu|Evet|
|[ISessionProperties](https://docs.microsoft.com/previous-versions/windows/desktop/ms713721(v=vs.85))|Zorunlu|Evet|
|[IAlterIndex](https://docs.microsoft.com/previous-versions/windows/desktop/ms714943(v=vs.85))|İsteğe Bağlı|Hayır|
|[IAlterTable](https://docs.microsoft.com/previous-versions/windows/desktop/ms719764(v=vs.85))|İsteğe Bağlı|Hayır|
|[IBindResource](https://docs.microsoft.com/previous-versions/windows/desktop/ms714936(v=vs.85))|İsteğe Bağlı|Hayır|
|[ICreateRow](https://docs.microsoft.com/previous-versions/windows/desktop/ms716832(v=vs.85))|İsteğe Bağlı|Hayır|
|[IDBCreateCommand](https://docs.microsoft.com/previous-versions/windows/desktop/ms711625(v=vs.85))|İsteğe Bağlı|Evet|
|[IDBSchemaRowset](https://docs.microsoft.com/previous-versions/windows/desktop/ms713686(v=vs.85))|İsteğe Bağlı|Evet|
|[IIndexDefinition](https://docs.microsoft.com/previous-versions/windows/desktop/ms711593(v=vs.85))|İsteğe Bağlı|Hayır|
|[ISupportErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/ms715816(v=vs.85))|İsteğe Bağlı|Evet|
|[ITableCreation](https://docs.microsoft.com/previous-versions/windows/desktop/ms713639(v=vs.85))|İsteğe Bağlı|Hayır|
|[ITableDefinition](https://docs.microsoft.com/previous-versions/windows/desktop/ms714277(v=vs.85))|İsteğe Bağlı|Hayır|
|[ITableDefinitionWithConstraints](https://docs.microsoft.com/previous-versions/windows/desktop/ms720947(v=vs.85))|İsteğe Bağlı|Hayır|
|[ITransaction](https://docs.microsoft.com/previous-versions/windows/desktop/ms723053(v=vs.85))|İsteğe Bağlı|Hayır|
|[ITransactionJoin](https://docs.microsoft.com/previous-versions/windows/desktop/ms718071(v=vs.85))|İsteğe Bağlı|Hayır|
|[ITransactionLocal](https://docs.microsoft.com/previous-versions/windows/desktop/ms714893(v=vs.85))|İsteğe Bağlı|Hayır|
|[ITransactionObject](https://docs.microsoft.com/previous-versions/windows/desktop/ms713659(v=vs.85))|İsteğe Bağlı|Hayır|

Oturum nesnesi bir satır kümesi nesnesi oluşturur. Oturum Sağlayıcı komutları destekliyorsa, ayrıca bir komut nesnesi oluşturur. (`CCommand`, OLE DB uygulama `TCommand`). Komut nesnesi uygulayan `ICommand` arabirimi ve kullanımları `ICommand::Execute` satır kümesinde, aşağıdaki resimde gösterildiği gibi komutları yürütmek için yöntemi.

![Sağlayıcı kavramsal diyagram](../../data/oledb/media/vc4u551.gif "sağlayıcısı kavramsal diyagramı")

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
