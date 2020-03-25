---
title: Yer İşaretlerini Kullanma
ms.date: 10/24/2018
helpviewer_keywords:
- rowsets, bookmarks
- OLE DB provider templates, bookmarks
- bookmarks, OLE DB
- OLE DB providers, bookmark support
ms.assetid: 7fa1d1a8-5063-4aa9-93ee-815bb9c98fae
ms.openlocfilehash: 5a4a2d65ba7367b5568603b5f08a07c6d85cc4a5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209321"
---
# <a name="using-bookmarks"></a>Yer İşaretlerini Kullanma

Satır kümesini açmadan önce, sağlayıcıya yer işaretlerini kullanmak istediğinizi söylemeniz gerekir. Bunu yapmak için, özellik kümesinde `DBPROP_BOOKMARKS` özelliğini **true** olarak ayarlayın. Sağlayıcı, yer işaretlerini sütun sıfır olarak alır, bu nedenle statik bir erişimci kullanıyorsanız özel makro BOOKMARK_ENTRY ve `CBookmark` sınıfını kullanmanız gerekir. `CBookmark`, bağımsız değişkenin, yer işareti arabelleğinin bayt cinsinden uzunluğu olduğu bir şablon sınıfıdır. Bir yer işareti için gereken arabellek uzunluğu sağlayıcıya bağlıdır. Aşağıdaki örnekte gösterildiği gibi ODBC OLE DB sağlayıcısını kullanıyorsanız, arabelleğin 4 bayt olması gerekir.

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

`CDynamicAccessor`kullanırsanız, arabellek çalışma zamanında dinamik olarak ayarlanır. Bu durumda, bir `CBookmark`, arabellek uzunluğu belirtmemenizi belirten özelleşmiş bir sürümünü kullanabilirsiniz. Aşağıdaki kod örneğinde gösterildiği gibi, geçerli kayıttaki yer işaretini almak için `GetBookmark` işlevini kullanın:

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

[Erişimcileri Kullanma](../../data/oledb/using-accessors.md)
