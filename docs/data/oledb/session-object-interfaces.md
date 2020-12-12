---
description: 'Daha fazla bilgi edinin: oturum nesnesi arabirimleri'
title: Oturum Nesnesi Arabirimleri
ms.date: 11/19/2018
helpviewer_keywords:
- session objects [OLE DB]
- session objects [OLE DB], interfaces
- OLE DB provider templates, object interfaces
- interfaces, session object
- interfaces, list of
ms.assetid: ac01a958-6dde-4bd7-8b63-94459e488335
ms.openlocfilehash: dc4f5644258b0ced4c97a5cda6de1b69abb8c2f1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286586"
---
# <a name="session-object-interfaces"></a>Oturum Nesnesi Arabirimleri

Aşağıdaki tabloda, bir oturum nesnesi için OLE DB tarafından tanımlanan zorunlu ve isteğe bağlı arabirimler gösterilmektedir.

|Arabirim|Gerekli mi?|OLE DB şablonlar tarafından uygulandı mu?|
|---------------|---------------|--------------------------------------|
|[IGetDataSource](/previous-versions/windows/desktop/ms709721(v=vs.85))|Zorunlu|Evet|
|[IOpenRowset](/previous-versions/windows/desktop/ms716946(v=vs.85))|Zorunlu|Evet|
|[ISessionProperties](/previous-versions/windows/desktop/ms713721(v=vs.85))|Zorunlu|Evet|
|[Ialterındex](/previous-versions/windows/desktop/ms714943(v=vs.85))|İsteğe Bağlı|Hayır|
|[Ialtertable](/previous-versions/windows/desktop/ms719764(v=vs.85))|İsteğe Bağlı|Hayır|
|[Ibindresource](/previous-versions/windows/desktop/ms714936(v=vs.85))|İsteğe Bağlı|Hayır|
|[Ireaterow](/previous-versions/windows/desktop/ms716832(v=vs.85))|İsteğe Bağlı|Hayır|
|[IDBCreateCommand](/previous-versions/windows/desktop/ms711625(v=vs.85))|İsteğe Bağlı|Evet|
|[IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85))|İsteğe Bağlı|Evet|
|[IIndexDefinition](/previous-versions/windows/desktop/ms711593(v=vs.85))|İsteğe Bağlı|Hayır|
|[Iupporterrorınfo](/previous-versions/windows/desktop/ms715816(v=vs.85))|İsteğe Bağlı|Evet|
|[Itableoluşturma](/previous-versions/windows/desktop/ms713639(v=vs.85))|İsteğe Bağlı|Hayır|
|[ITableDefinition](/previous-versions/windows/desktop/ms714277(v=vs.85))|İsteğe Bağlı|Hayır|
|[Itabledefinitionwithkısıtlamalar](/previous-versions/windows/desktop/ms720947(v=vs.85))|İsteğe Bağlı|Hayır|
|[ITransaction](/previous-versions/windows/desktop/ms723053(v=vs.85))|İsteğe Bağlı|Hayır|
|[Itransactionjoın](/previous-versions/windows/desktop/ms718071(v=vs.85))|İsteğe Bağlı|Hayır|
|[ITransactionLocal](/previous-versions/windows/desktop/ms714893(v=vs.85))|İsteğe Bağlı|Hayır|
|[Ictionobject](/previous-versions/windows/desktop/ms713659(v=vs.85))|İsteğe Bağlı|Hayır|

Oturum nesnesi bir satır kümesi nesnesi oluşturur. Sağlayıcı komutları destekliyorsa, oturum da bir komut nesnesi ( `CCommand` OLE DB uygulayarak `TCommand` ) oluşturur. Komut nesnesi `ICommand` arabirimini uygular ve `ICommand::Execute` aşağıdaki şekilde gösterildiği gibi, satır kümesinde komutları yürütmek için yöntemini kullanır.

![Sağlayıcı kavramsal diyagramı](../../data/oledb/media/vc4u551.gif "Sağlayıcı kavramsal diyagramı")

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonu mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
