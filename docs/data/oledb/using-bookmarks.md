---
title: Yer İşaretlerini Kullanma
ms.date: 10/24/2018
helpviewer_keywords:
- rowsets, bookmarks
- OLE DB provider templates, bookmarks
- bookmarks, OLE DB
- OLE DB providers, bookmark support
ms.assetid: 7fa1d1a8-5063-4aa9-93ee-815bb9c98fae
ms.openlocfilehash: 1f8ef4c25ad921dad66e5587f4005585b3e017f5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50635662"
---
# <a name="using-bookmarks"></a>Yer İşaretlerini Kullanma

Satır kümesi açmadan önce yer işaretlerini kullanmak istediğiniz sağlayıcı söylemeniz gerekir. Bunu yapmak için ayarlanmış `DBPROP_BOOKMARKS` özelliğini **true** , özelliğini ayarlayın. Sağlayıcı özel BOOKMARK_ENTRY makrosu kullanmalısınız sütun sıfır olarak yer işaretleri alır ve `CBookmark` statik erişimci kullanıyorsanız, sınıf. `CBookmark` bağımsız değişken yer işareti arabelleğin bayt cinsinden uzunluğu olduğu bir şablon sınıfıdır. Bir yer işareti için gerekli arabellek uzunluğu sağlayıcısına bağlıdır. Aşağıdaki örnekte gösterildiği gibi ODBC OLE DB sağlayıcısı kullanıyorsanız, arabellek 4 bayt olması gerekir.

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

Kullanırsanız `CDynamicAccessor`, arabellek çalışma zamanında dinamik olarak ayarlanır. Bu durumda, özelleştirilmiş bir sürümünü kullanabilirsiniz `CBookmark` , yoksa belirttiğiniz bir arabellek uzunluğu. İşlevini `GetBookmark` Bu kod örneğinde gösterildiği gibi geçerli kayıtta yer almak için:

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

Yer işaretleri sağlayıcı belirtilen bölümler destekleme hakkında daha fazla bilgi için bkz: [yer işaretleri sağlayıcı desteği](../../data/oledb/provider-support-for-bookmarks.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Erişimcileri Kullanma](../../data/oledb/using-accessors.md)