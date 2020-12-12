---
description: 'Hakkında daha fazla bilgi edinin: yer Işaretlerini kullanma'
title: Yer İşaretlerini Kullanma
ms.date: 10/24/2018
helpviewer_keywords:
- rowsets, bookmarks
- OLE DB provider templates, bookmarks
- bookmarks, OLE DB
- OLE DB providers, bookmark support
ms.assetid: 7fa1d1a8-5063-4aa9-93ee-815bb9c98fae
ms.openlocfilehash: d0cf27a5f93b3e6b00fa6f8cbb69ae7414f4d819
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319163"
---
# <a name="using-bookmarks"></a>Yer İşaretlerini Kullanma

Satır kümesini açmadan önce, sağlayıcıya yer işaretlerini kullanmak istediğinizi söylemeniz gerekir. Bunu yapmak için özelliği `DBPROP_BOOKMARKS` **`true`** özellik kümesi içinde olarak ayarlayın. Sağlayıcı, yer işaretlerini sütun sıfır olarak alır, bu yüzden statik erişimci kullanıyorsanız özel makro BOOKMARK_ENTRY ve `CBookmark` sınıfını kullanmanız gerekir. `CBookmark` , bağımsız değişkenin, yer işareti arabelleğinin bayt cinsinden uzunluğu olduğu bir şablon sınıfıdır. Bir yer işareti için gereken arabellek uzunluğu sağlayıcıya bağlıdır. Aşağıdaki örnekte gösterildiği gibi ODBC OLE DB sağlayıcısını kullanıyorsanız, arabelleğin 4 bayt olması gerekir.

```cpp
class CProducts
{
public:
   CBookmark<4> bookmark;

   BEGIN_COLUMN_MAP(CProducts)
      BOOKMARK_ENTRY(bookmark)
   END_COLUMN_MAP()
};
```

Ardından, aşağıdaki kod tarafından kullanılır:

```cpp
CDBPropSet propset(DBPROPSET_ROWSET);
propset.AddProperty(DBPROP_BOOKMARKS, true);

CTable<CAccessor<CProducts>> product;
CSession session;
product.Open(session, "Products", &propset);
```

Kullanırsanız `CDynamicAccessor` , arabellek çalışma zamanında dinamik olarak ayarlanır. Bu durumda, `CBookmark` bir arabellek uzunluğu belirtmezseniz özel bir sürümünü kullanabilirsiniz. `GetBookmark`Aşağıdaki kod örneğinde gösterildiği gibi, geçerli kayıttaki yer işaretini almak için işlevini kullanın:

```cpp
CTable<CDynamicAccessor> product;
CBookmark<> bookmark;
CDBPropSet propset(DBPROPSET_ROWSET);
CSession session;

propset.AddProperty(DBPROP_BOOKMARKS, true);
product.Open(session, "Products", &propset);
product.MoveNext();
product.GetBookmark(&bookmark);
```

Sağlayıcılardaki yer imlerini destekleme hakkında daha fazla bilgi için bkz. [yer işaretleri Için sağlayıcı desteği](../../data/oledb/provider-support-for-bookmarks.md).

## <a name="see-also"></a>Ayrıca bkz.

[Erişimcileri kullanma](../../data/oledb/using-accessors.md)
