---
description: 'Hakkında daha fazla bilgi edinin: Sağlayıcınızdaki bir özelliğe başvurma'
title: Sağlayıcınızdaki Bir Özelliğe Başvurma
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB providers, properties
- references, to properties in providers
- referencing properties in providers
ms.assetid: bfbb3851-5eed-467a-a179-4a97a9515525
ms.openlocfilehash: dfc3b06820b98477a033b450d42feca52c5c7a72
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286624"
---
# <a name="referencing-a-property-in-your-provider"></a>Sağlayıcınızdaki Bir Özelliğe Başvurma

İstediğiniz özelliğin özellik grubunu ve özellik KIMLIĞINI bulun. Daha fazla bilgi için, **OLE DB Programcı başvurusunda** [OLE DB Özellikler](/previous-versions/windows/desktop/ms722734(v=vs.85)) ' i inceleyin.

Aşağıdaki örnek, satır kümesinden bir özelliği almaya çalıştığımız varsayılmaktadır. Oturumu veya komutu kullanmanın kodu benzerdir, ancak farklı bir arabirim kullanır.

Oluşturucuya parametre olarak özellik grubunu kullanarak bir [CDBPropSet](../../data/oledb/cdbpropset-class.md) nesnesi oluşturun. Örneğin:

```cpp
CDBPropSet propset(DBPROPSET_ROWSET);
```

Özellik KIMLIĞI ve özelliğe atanacak bir değer geçirerek [AddProperty](./cdbpropset-class.md#addproperty)çağrısı yapın. Değerin türü, kullanmakta olduğunuz özelliğe bağlıdır.

```cpp
CDBPropSet propset(DBPROPSET_ROWSET);

propset.AddProperty(DBPROP_IRowsetChange, true);

propset.AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_INSERT | DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_DELETE);
```

`IRowset`Çağırmak için arabirimini kullanın `GetProperties` . Özellik kümesini parametre olarak geçirin. Son kod şu şekildedir:

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

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonlarıyla çalışma](../../data/oledb/working-with-ole-db-provider-templates.md)
