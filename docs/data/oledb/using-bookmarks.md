---
title: Yer işaretlerini kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- rowsets, bookmarks
- OLE DB provider templates, bookmarks
- bookmarks, OLE DB
- OLE DB providers, bookmark support
ms.assetid: 7fa1d1a8-5063-4aa9-93ee-815bb9c98fae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8643b8150f08191fa041107fa4a88e3cbcf2964a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46042266"
---
# <a name="using-bookmarks"></a>Yer İşaretlerini Kullanma

Satır kümesi açmadan önce yer işaretlerini kullanmak istediğiniz sağlayıcı söylemeniz gerekir. Bunu yapmak için ayarlanmış `DBPROP_BOOKMARKS` özelliğini **true** , özelliğini ayarlayın. Sağlayıcı özel BOOKMARK_ENTRY makrosu kullanmalısınız sütun sıfır olarak yer işaretleri alır ve `CBookmark` statik erişimci kullanıyorsanız sınıfı. `CBookmark` bağımsız değişken yer işareti arabelleğin bayt cinsinden uzunluğu olduğu bir şablon sınıfıdır. Bir yer işareti için gerekli arabellek uzunluğu sağlayıcısına bağlıdır. Aşağıdaki örnekte gösterildiği gibi ODBC OLE DB sağlayıcısı kullanıyorsanız, arabellek 4 bayt olması gerekir.  
  
```cpp  
class CProducts  
{  
public:  
   CBookmark<4>   bookmark;  
  
   BEGIN_COLUMN_MAP(CProducts)  
      BOOKMARK_ENTRY(bookmark)  
   END_COLUMN_MAP()  
};  
  
CDBPropSet propset(DBPROPSET_ROWSET);  

propset.AddProperty(DBPROP_BOOKMARKS, true);  
  

CTable<CAccessor<CProducts>> product;  
product.Open(session, "Products", &propset);  
```  
  
Kullanırsanız `CDynamicAccessor`, arabellek çalışma zamanında dinamik olarak ayrılır. Bu durumda, özelleştirilmiş bir sürümünü kullanabilirsiniz `CBookmark` kendisi için değil belirttiğiniz bir arabellek uzunluğu. İşlevini `GetBookmark` Bu kod örneğinde gösterildiği gibi geçerli kayıtta yer almak için:  
  
```cpp  
CTable<CDynamicAccessor> product;  
CBookmark<>              bookmark;  
CDBPropSet propset(DBPROPSET_ROWSET);  
  

propset.AddProperty(DBPROP_BOOKMARKS, true);  

product.Open(session, "Products", &propset);  

product.MoveNext();  

product.GetBookmark(&bookmark);  
```  
  
Yer işaretleri sağlayıcı belirtilen bölümler destekleme hakkında daha fazla bilgi için bkz: [yer işaretleri sağlayıcı desteği](../../data/oledb/provider-support-for-bookmarks.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[Erişimcileri Kullanma](../../data/oledb/using-accessors.md)