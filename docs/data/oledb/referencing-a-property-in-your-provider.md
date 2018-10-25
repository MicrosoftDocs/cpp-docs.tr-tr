---
title: Sağlayıcınızdaki bir özelliğe başvurma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, properties
- references, to properties in providers
- referencing properties in providers
ms.assetid: bfbb3851-5eed-467a-a179-4a97a9515525
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e88dcc168df6b6b315f73e2eb595f55668fd2493
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50074871"
---
# <a name="referencing-a-property-in-your-provider"></a>Sağlayıcınızdaki Bir Özelliğe Başvurma

Özellik kimliği ve özellik grubu istediğiniz özelliği bulun. Daha fazla bilgi için [OLE DB özellikleri](/previous-versions/windows/desktop/ms722734) içinde *OLE DB Programcının Başvurusu*.

Aşağıdaki örnek, satır kümesinden bir özellik get yapılmaya çalışılırken varsayar. Oturum ya da komutu kullanmak için kodu, benzer ancak farklı bir arabirim kullanır.

Oluşturma bir [CDBPropSet](../../data/oledb/cdbpropset-class.md) oluşturucusuna parametre olarak özellik grubunu kullanarak nesne. Örneğin:

```cpp
CDBPropSet propset(DBPROPSET_ROWSET);
```

Çağrı [AddProperty](../../data/oledb/cdbpropset-addproperty.md), özellik kimliği ve bir değer özelliğe atanacak geçirme. Değerin türü, kullanmakta olduğunuz özelliğine bağlıdır.

```cpp
CDBPropSet propset(DBPROPSET_ROWSET);

propset.AddProperty(DBPROP_IRowsetChange, true);

propset.AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_INSERT | DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_DELETE);
```

Kullanım `IRowset` çağrılacak arabirimi `GetProperties`. Bir parametre özelliği geçirin. Son kod aşağıdaki gibidir:

```cpp
CAgentRowset<CCustomCommand>* pRowset = (CAgentRowset<CCustomCommand>*) pThis;

CComQIPtr<IRowsetInfo, &IID_IRowsetInfo> spRowsetProps = pRowset;

DBPROPIDSET set;
set.AddPropertyID(DBPROP_BOOKMARKS);

DBPROPSET* pPropSet = NULL;
ULONG ulPropSet = 0;

HRESULT hr;

if (spRowsetProps)
   hr = spRowsetProps->GetProperties(1, &set, &ulPropSet, &pPropSet);

if (pPropSet)
{
   CComVariant var = pPropSet->rgProperties[0].vValue;
   CoTaskMemFree(pPropSet->rgProperties);
   CoTaskMemFree(pPropSet);

   if (SUCCEEDED(hr) && (var.boolVal == VARIANT_TRUE))
   {
      ...  // Use property here
   }
}
```

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Sağlayıcı Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-provider-templates.md)