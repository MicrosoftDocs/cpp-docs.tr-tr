---
title: db_accessor | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.db_accessor
dev_langs: C++
helpviewer_keywords: db_accessor attribute
ms.assetid: ec407a9f-24d7-4822-96d4-7cc6a0301815
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d5293712990685ff63bcafa8e5c9d5a0e8592a25
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="dbaccessor"></a>db_accessor
Grupları **db_column** katılan öznitelikleri `IAccessor`-bağlama dayalı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ db_accessor(   
   num,   
   auto   
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 *NUM*  
 Erişimci sayısını (sıfır tabanlı bir tamsayı dizini) belirtir. Artan erişimcisi numaraları tamsayılar kullanarak azalan veya değerleri tanımlanan belirtmeniz gerekir.  
  
 *Otomatik*  
 Erişimci otomatik olarak alınır olup olmadığını belirten bir Boole değeri (**TRUE**) veya alınamaz (**FALSE**).  
  
## <a name="remarks"></a>Açıklamalar  
 **db_accessor** için temel alınan OLE DB erişimci tanımlar sonraki **db_column** ve **db_param** aynı sınıfı veya işlevi içinden öznitelikleri. **db_accessor** üye düzeyinde kullanılabilir ve kullanılan grubuna **db_column** OLE DB'de katılmak öznitelikleri `IAccessor`-bağlama dayalı. Ya da ile birlikte kullanılan **db_table** veya **db_command** öznitelikleri. Bu öznitelik çağırma benzer arama için [BEGIN_ACCESSOR](../data/oledb/begin-accessor.md) ve [END_ACCESSOR](../data/oledb/end-accessor.md) makroları.  
  
 **db_accessor** bir satır kümesi oluşturur ve karşılık gelen erişimcisi eşlemeleri bağlar. Değil çağırırsanız **db_accessor**erişimci 0 otomatik olarak oluşturulur ve tüm sütun bağlamaları bu erişimcisi bloğuna eşleşecektir.  
  
 **db_accessor** gruplar bir veya daha fazla erişimciler içine sütun bağlamaları veritabanı. İçinde gereken çoklu erişimci kullanma senaryolarda bir tartışma için bkz: [bir satır kümesi üzerinde Çoklu Erişimci Kullanma](../data/oledb/using-multiple-accessors-on-a-rowset.md). "Kullanıcı kaydı desteği için çoklu erişimci" Ayrıca bakın [kullanıcı kayıtlarını](../data/oledb/user-records.md).  
  
 Tüketici özniteliği sağlayıcısı bu öznitelik bir sınıfa uyguladığında derleyici sınıfa adlandıracak \_ *YourClassName*erişimci nerede *YourClassName* verdiğiniz adı sınıf ve derleyici adlı bir sınıf oluşturur de *YourClassName*, den türetilen \_ *YourClassName*erişimcisi.  Sınıf Görünümü'nde, her iki sınıfları görürsünüz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır **db_accessor** Grup sütunlarından Siparişler tablosundaki iki erişimciler Northwind veritabanına için. Erişimci 0 otomatik erişimci ve erişimci 1 değil.  
  
```  
// cpp_attr_ref_db_accessor.cpp  
// compile with: /LD /link /OPT:NOREF  
#define _ATL_ATTRIBUTES  
#include <atlbase.h>  
#include <atldbcli.h>  
  
[ db_command(L"SELECT LastName, FirstName FROM Orders") ]  
class CEmployees {  
public:  
   [ db_accessor(0, TRUE) ];  
   [ db_column("1") ] LONG m_OrderID;  
   [ db_column("2") ] TCHAR m_CustomerID[6];  
   [ db_column("4") ] DBTIMESTAMP m_OrderDate;   
  
   [ db_accessor(1, FALSE) ];  
   [ db_column("8") ] CURRENCY m_Freight;  
};  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|Öznitelik blokları|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB tüketici öznitelikleri](../windows/ole-db-consumer-attributes.md)   
