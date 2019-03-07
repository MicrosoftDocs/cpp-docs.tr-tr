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
ms.openlocfilehash: 7e8a9cd204a07afc2b14c6a1e31e7c970c27cfc2
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57423384"
---
# <a name="session-object-interfaces"></a>Oturum Nesnesi Arabirimleri

Aşağıdaki tabloda, bir oturum nesnesi için OLE DB tarafından tanımlanan zorunlu ve isteğe bağlı arabirimler gösterilir.

|Arabirim|Gerekli mi?|OLE DB Şablonları tarafından uygulanır?|
|---------------|---------------|--------------------------------------|
|[IGetDataSource](/previous-versions/windows/desktop/ms709721(v=vs.85))|Zorunlu|Evet|
|[IOpenRowset](/previous-versions/windows/desktop/ms716946(v=vs.85))|Zorunlu|Evet|
|[ISessionProperties](/previous-versions/windows/desktop/ms713721(v=vs.85))|Zorunlu|Evet|
|[IAlterIndex](/previous-versions/windows/desktop/ms714943(v=vs.85))|İsteğe Bağlı|Hayır|
|[IAlterTable](/previous-versions/windows/desktop/ms719764(v=vs.85))|İsteğe Bağlı|Hayır|
|[IBindResource](/previous-versions/windows/desktop/ms714936(v=vs.85))|İsteğe Bağlı|Hayır|
|[ICreateRow](/previous-versions/windows/desktop/ms716832(v=vs.85))|İsteğe Bağlı|Hayır|
|[IDBCreateCommand](/previous-versions/windows/desktop/ms711625(v=vs.85))|İsteğe Bağlı|Evet|
|[IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85))|İsteğe Bağlı|Evet|
|[IIndexDefinition](/previous-versions/windows/desktop/ms711593(v=vs.85))|İsteğe Bağlı|Hayır|
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816(v=vs.85))|İsteğe Bağlı|Evet|
|[ITableCreation](/previous-versions/windows/desktop/ms713639(v=vs.85))|İsteğe Bağlı|Hayır|
|[ITableDefinition](/previous-versions/windows/desktop/ms714277(v=vs.85))|İsteğe Bağlı|Hayır|
|[ITableDefinitionWithConstraints](/previous-versions/windows/desktop/ms720947(v=vs.85))|İsteğe Bağlı|Hayır|
|[ITransaction](/previous-versions/windows/desktop/ms723053(v=vs.85))|İsteğe Bağlı|Hayır|
|[ITransactionJoin](/previous-versions/windows/desktop/ms718071(v=vs.85))|İsteğe Bağlı|Hayır|
|[ITransactionLocal](/previous-versions/windows/desktop/ms714893(v=vs.85))|İsteğe Bağlı|Hayır|
|[ITransactionObject](/previous-versions/windows/desktop/ms713659(v=vs.85))|İsteğe Bağlı|Hayır|

Oturum nesnesi bir satır kümesi nesnesi oluşturur. Oturum Sağlayıcı komutları destekliyorsa, ayrıca bir komut nesnesi oluşturur. (`CCommand`, OLE DB uygulama `TCommand`). Komut nesnesi uygulayan `ICommand` arabirimi ve kullanımları `ICommand::Execute` satır kümesinde, aşağıdaki resimde gösterildiği gibi komutları yürütmek için yöntemi.

![Sağlayıcı kavramsal diyagram](../../data/oledb/media/vc4u551.gif "sağlayıcısı kavramsal diyagramı")

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
