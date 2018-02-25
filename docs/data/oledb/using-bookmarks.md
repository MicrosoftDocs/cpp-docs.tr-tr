---
title: "Yer işaretlerini kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- rowsets, bookmarks
- OLE DB provider templates, bookmarks
- bookmarks, OLE DB
- OLE DB providers, bookmark support
ms.assetid: 7fa1d1a8-5063-4aa9-93ee-815bb9c98fae
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 18c3f8cfb77e9bcd0719fd7130441f628df6eb58
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="using-bookmarks"></a>Yer İşaretlerini Kullanma
Satır kümesi açmadan önce yer işaretleri kullanmak istediğiniz sağlayıcı bildirmeniz gerekir. Bunu yapmak için ayarlayın **DBPROP_BOOKMARKS** özelliğine **doğru** , özelliğini ayarlayın. Özel makrosu kullanmalısınız sağlayıcı yer işaretlerini sütun sıfır olarak alır. `BOOKMARK_ENTRY` ve `CBookmark` statik erişimci kullanıyorsanız sınıfı. `CBookmark` bağımsız değişkeni yer işareti arabelleğinin bayt cinsinden uzunluğu olduğu bir şablon sınıfıdır. Yer işareti için gerekli olan arabellek uzunluğu sağlayıcısına bağlıdır. Aşağıdaki örnekte gösterildiği gibi ODBC OLE DB Sağlayıcısı'nı kullanıyorsanız, arabellek 4 bayt olmalıdır.  
  
```  
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
  
 Kullanırsanız `CDynamicAccessor`, arabellek çalışma zamanında dinamik olarak ayrılır. Bu durumda, özelleştirilmiş bir sürümünü kullanabilirsiniz `CBookmark` kendisi için değil belirttiğiniz arabellek uzunluğu. İşlevini `GetBookmark` Bu kod örneğinde gösterildiği gibi geçerli kaydından yer almak için:  
  
```  
CTable<CDynamicAccessor> product;  
CBookmark<>              bookmark;  
CDBPropSet propset(DBPROPSET_ROWSET);  
  

propset.AddProperty(DBPROP_BOOKMARKS, true);  

product.Open(session, "Products", &propset);  

product.MoveNext();  

product.GetBookmark(&bookmark);  
```  
  
 Yer işaretleri sağlayıcı destekleme hakkında daha fazla bilgi için bkz: [yer işaretleri sağlayıcı desteği](../../data/oledb/provider-support-for-bookmarks.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Erişimcileri Kullanma](../../data/oledb/using-accessors.md)