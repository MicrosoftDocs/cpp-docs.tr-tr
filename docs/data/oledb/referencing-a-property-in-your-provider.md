---
title: Sağlayıcınızdaki Bir Özelliğe Başvurma
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB providers, properties
- references, to properties in providers
- referencing properties in providers
ms.assetid: bfbb3851-5eed-467a-a179-4a97a9515525
ms.openlocfilehash: d70a1901c457d9fbdbe8712d84999e256a54d0c2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209805"
---
# <a name="referencing-a-property-in-your-provider"></a>Sağlayıcınızdaki Bir Özelliğe Başvurma

İstediğiniz özelliğin özellik grubunu ve özellik KIMLIĞINI bulun. Daha fazla bilgi için, **OLE DB Programcı başvurusunda** [OLE DB Özellikler](/previous-versions/windows/desktop/ms722734(v=vs.85)) ' i inceleyin.

Aşağıdaki örnek, satır kümesinden bir özelliği almaya çalıştığımız varsayılmaktadır. Oturumu veya komutu kullanmanın kodu benzerdir, ancak farklı bir arabirim kullanır.

Oluşturucuya parametre olarak özellik grubunu kullanarak bir [CDBPropSet](../../data/oledb/cdbpropset-class.md) nesnesi oluşturun. Örneğin:

```cpp
CDBPropSet propset(DBPROPSET_ROWSET);
```

Özellik KIMLIĞI ve özelliğe atanacak bir değer geçirerek [AddProperty](../../data/oledb/cdbpropset-addproperty.md)çağrısı yapın. Değerin türü, kullanmakta olduğunuz özelliğe bağlıdır.

```cpp
CDBPropSet propset(DBPROPSET_ROWSET);

propset.AddProperty(DBPROP_IRowsetChange, true);

propset.AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_INSERT | DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_DELETE);
```

`GetProperties`çağırmak için `IRowset` arabirimini kullanın. Özellik kümesini parametre olarak geçirin. Son kod şu şekildedir:

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

[OLE DB Sağlayıcı Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-provider-templates.md)
