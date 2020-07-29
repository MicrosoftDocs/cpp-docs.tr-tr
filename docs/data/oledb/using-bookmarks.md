---
title: Yer İşaretlerini Kullanma
ms.date: 10/24/2018
helpviewer_keywords:
- rowsets, bookmarks
- OLE DB provider templates, bookmarks
- bookmarks, OLE DB
- OLE DB providers, bookmark support
ms.assetid: 7fa1d1a8-5063-4aa9-93ee-815bb9c98fae
ms.openlocfilehash: 8caa33b3bafbaa9e537d9669aa7b60a9355475ef
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218305"
---
# <a name="using-bookmarks"></a>Yer İşaretlerini Kullanma

Satır kümesini açmadan önce, sağlayıcıya yer işaretlerini kullanmak istediğinizi söylemeniz gerekir. Bunu yapmak için özelliği `DBPROP_BOOKMARKS` **`true`** özellik kümesi içinde olarak ayarlayın. Sağlayıcı, yer işaretlerini sütun sıfır olarak alır, bu yüzden statik erişimci kullanıyorsanız özel makro BOOKMARK_ENTRY ve `CBookmark` sınıfını kullanmanız gerekir. `CBookmark`, bağımsız değişkenin, yer işareti arabelleğinin bayt cinsinden uzunluğu olduğu bir şablon sınıfıdır. Bir yer işareti için gereken arabellek uzunluğu sağlayıcıya bağlıdır. Aşağıdaki örnekte gösterildiği gibi ODBC OLE DB sağlayıcısını kullanıyorsanız, arabelleğin 4 bayt olması gerekir.

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
