---
title: Şema satır kümeleri ile meta verileri alma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- schema rowsets, getting OLE DB provider metadata
- OLE DB consumer templates, getting provider metadata
- metadata, getting (OLE DB Templates)
ms.assetid: 6b448461-82fb-4acf-816b-3cbb0ca1d186
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 60bed04015060bd65f4d4c771a228e3b50c3486e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057112"
---
# <a name="obtaining-metadata-with-schema-rowsets"></a>Şema Satır Kümeleri ile Meta Verileri Alma

Bazen satır kümesi açmaya gerek kalmadan sağlayıcısı, satır, tablo, sütun veya diğer veritabanı bilgileri hakkında bilgi edinmek gerekir. Veritabanı yapısı hakkında daha fazla veri meta veri adı verilir ve bir dizi farklı yöntem tarafından alınabilir. Bir şema satır kümeleri kullanmaktır.  
  
OLE DB Şablonları, şema bilgileri almak için sınıf kümesi sağlar; Bu sınıflar önceden tanımlı bir şema satır kümeleri oluşturma ve listelenen [şeması satır kümesi sınıfları ve Typedef sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md).  
  
> [!NOTE]
>  OLAP kullanıyorsanız ve bazı kümeleriniz şeması satır kümesi sınıfları tarafından desteklenmez (örneğin, değişken sayıda sütuna sahip), kullanmayı düşünmelisiniz `CManualAccessor` veya `CDynamicAccessor`. Sütunlarda kaydırın ve her sütun için olası veri türlerini işlemek için case deyimleri kullanın.  
  
## <a name="catalogschema-model"></a>Katalog/şema modeli  

ANSI SQL veri depoları için bir katalog/şeması modeli tanımlar; OLE DB, bu modeli kullanır. Bu modelde, şemalar katalogları (veritabanları) içerir ve şemalar tabloları içerir.  
  
- **Katalog** bir katalog veritabanı için başka bir addır. İlişkili şemalar koleksiyonudur. Belirtilen veri kaynağına ait katalogları (veritabanları) listelemek için kullanın [CCatalog](../../data/oledb/ccatalogs-ccataloginfo.md). Çok sayıda veritabanında yalnızca bir katalog olduğundan meta veriler bazen yalnızca şema bilgileri çağrılır.  
  
- **Şema** bir şemaya sahip olduğu veya belirli bir kullanıcı tarafından oluşturulan veritabanı nesneleri koleksiyonudur. Belirli bir kullanıcıya ait şemaları listelemek için kullanın [CSchemata](../../data/oledb/cschemata-cschematainfo.md).  
  
     Microsoft SQL Server ve ODBC 2.x bağlamında, bir şema bir sahibi olması (örneğin, dbo bir tipik şema adıdır). Ayrıca, SQL Server tabloları kümesi içinde meta verileri depolar: bir tablo içerdiği tüm tabloların bir listesini ve başka bir tablonun tüm sütunları listesini içerir. Bir Microsoft Access veritabanındaki bir şemada eşdeğeri yoktur.  
  
- **Tablo** tablolarıdır belirli bir sırada düzenlenmiş sütun koleksiyonu. Belirtilen katalog (veritabanı) ve bu tablolar hakkında bilgi tanımlanan tablolarını listelemek için kullanın [CTables](../../data/oledb/ctables-ctableinfo.md)).  
  
## <a name="restrictions"></a>Kısıtlamalar  

Şema bilgileri sorgulandığında, kısıtlamaları, ilgilendiğiniz bilgi türünü belirtmek için kullanabilirsiniz. Kısıtlamaları bir filtre veya sorguda Niteleyici olarak düşünebilirsiniz. Örneğin, sorgu içinde:  
  
```sql  
SELECT * FROM authors where l_name = 'pivo'  
```  
  
`l_name` bir kısıtlaması yoktur. Bu, yalnızca bir kısıtlama ile çok basit bir örnektir; Şema satır kümesi sınıfları birkaç kısıtlama destekler.  
  
[Şeması satır kümesi typedef sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) örnekleme ve onu açarak bir şeması satır kümesi gibi başka bir satır kümesi erişebilmeleri tüm OLE DB şema satır kümeleri kapsüller. Örneğin, typedef sınıfı [CColumns](../../data/oledb/ccolumns-ccolumnsinfo.md) olarak tanımlanır:  
  
```cpp  
CRestrictions<CAccessor<CColumnsInfo>  
```  
  
[CRestrictions](../../data/oledb/crestrictions-class.md) sınıf kısıtlama desteği sağlar. Şema satır kümesi örneğini oluşturduktan sonra çağrı [CRestrictions::Open](../../data/oledb/crestrictions-open.md). Bu yöntem, belirttiğiniz kısıtlamalara göre bir sonuç kümesi döndürür.  
  
Kısıtlamaları belirtmek için başvurmak [ek B: şema satır kümeleri](/previous-versions/windows/desktop/ms712921\(v=vs.85\)) ve kullanmakta olduğunuz satır kümesini bakın. Örneğin, `CColumns` karşılık gelen [SÜTUNLARIN satır](/previous-versions/windows/desktop/ms723052\(v%3dvs.85\)); Bu konu SÜTUNLARIN satır kısıtlama sütunları listeler: TABLE_CATALOG TABLE_SCHEMA, TABLE_NAME, COLUMN_NAME. Bu sipariş kısıtlamalarınız belirtilirken izlemeniz gerekir.  
  
Bu nedenle, örneğin, tablo adı ile kısıtlamak istiyorsanız, TABLE_NAME üçüncü kısıtlama sütunu olduğuna dikkat edin ve sonra çağrı `Open`, aşağıdaki örnekte gösterildiği gibi üçüncü kısıtlama parametresi olarak istenen tablo adını belirtme.  
  
#### <a name="to-use-schema-rowsets"></a>Şema satır kümeleri kullanmak için  
  
1. Üst bilgi dosyası Atldbsch.h içermelidir (Kuşkusuz, tüketici desteği de Atldbcli.h gerekir).  
  
1. Bir şema satır kümesi nesnesi tüketicinin veya belgenin üst bilgi dosyası. Tablo bilgileri almak istiyorsanız, bildirmek bir `CTables` sütun bilgileri almak istiyorsanız, bildirme; nesnesi bir `CColumns` nesne. Bu örnek, nasıl yazarlar tablodaki sütunlar alınacağını gösterir:  
  
    ```cpp  
    CDataSource ds;  
    ds.Open();  
    CSession ss;  
    ss.Open();  
    CColumns ColumnSchemaRowset;  
    // TABLE_NAME is the third restriction column, so  
    // specify "authors" as the third restriction parameter:  
    hr = ColumnSchemaRowset.Open(ss, NULL, NULL, "authors");  
    hr = ColumnSchemaRowset.MoveFirst();  
    while (hr == S_OK)  
    {  
       hr = ColumnSchemaRowset.MoveNext();  
    }  
    ```  
  
1. Bilgileri getirmek için uygun veri üyesi şeması satır kümesi nesnesi, örneğin, erişim `ColumnSchemaRowset.m_szColumnName`. Bu, COLUMN_NAME'e karşılık gelir. Her veri üyesi karşılık gelen için OLE DB sütunu için bkz [CColumns](../../data/oledb/ccolumns-ccolumnsinfo.md).  
  
Şema satır kümesi başvurusu için typedef sınıfları, OLE DB Şablonları sağlanan (bkz [şeması satır kümesi sınıfları ve Typedef sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)).  
  
Kısıtlama sütunları içeren OLE DB şema satır kümeleri hakkında daha fazla bilgi için bkz. [ek B: şema satır kümeleri](/previous-versions/windows/desktop/ms712921\(v=vs.85\)) OLE DB Programcı Başvurusu.  
  
Şema satır kümesi sınıflarını kullanmayı daha karmaşık örnekleri için bkz: [CatDB](https://github.com/Microsoft/VCSamples) ve [DBVIEWER](https://github.com/Microsoft/VCSamples) örnekleri.  
  
Şema satır kümeleri için sağlayıcı desteği hakkında daha fazla bilgi için bkz: [şema satır kümelerini destekleme](../../data/oledb/supporting-schema-rowsets.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[Erişimcileri Kullanma](../../data/oledb/using-accessors.md)