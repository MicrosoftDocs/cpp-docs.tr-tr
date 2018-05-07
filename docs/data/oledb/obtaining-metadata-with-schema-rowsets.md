---
title: Şema satır kümeleri ile meta veri alma | Microsoft Docs
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
ms.openlocfilehash: da5a715be2ac6dc94ace25ee98781d2e9a4c5f8e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="obtaining-metadata-with-schema-rowsets"></a>Şema Satır Kümeleri ile Meta Verileri Alma
Bazen satır açmadan sağlayıcı, satır, tablo, sütun veya diğer veritabanı bilgileri hakkında bilgi edinmeniz gerekir. Veri veritabanı yapısı hakkındaki meta veriler denir ve çeşitli farklı yöntemler tarafından alınabilir. Şema satır kümeleri kullanan bir yöntemdir.  
  
 OLE DB Şablonları şema bilgileri almak için sınıf kümesi sağlar; Bu sınıfların önceden tanımlanmış şema satır kümeleri oluşturma ve listelenen [şema satır kümesi sınıfları ve Typedef sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md).  
  
> [!NOTE]
>  OLAP kullanıyorsanız ve bazı kümeleriniz şema satır kümesi sınıfları tarafından desteklenmeyen (örneğin, değişken sayıda sütuna sahip), kullanmayı düşünmelisiniz `CManualAccessor` veya `CDynamicAccessor`. Sütunlarda kaydırın ve case deyimleri her sütun için olası veri türlerini yönetmek için kullanın.  
  
## <a name="catalogschema-model"></a>Katalog/şema modeli  
 ANSI SQL veri depoları için katalog/şema modeli tanımlar; OLE DB bu modeli kullanır. Bu modelde, şemalar katalogları (veritabanları) içerir ve şemalar tabloları içerir.  
  
-   **Katalog** bir veritabanı için başka bir ad kataloğudur. İlişkili şemalar koleksiyonudur. Verilen veri kaynağına ait katalogları (veritabanları) listelemek için kullanmak [CCatalog](../../data/oledb/ccatalogs-ccataloginfo.md). Birçok veritabanı yalnızca bir katalog bulunduğundan, meta veri bazen yalnızca şema bilgileri adı verilir.  
  
-   **Şema** bir şemaya sahip olduğu veya belirli bir kullanıcı tarafından oluşturulan veritabanı nesneleri koleksiyonudur. Belirli bir kullanıcıya ait şemaları listelemek için kullanın [CSchemata](../../data/oledb/cschemata-cschematainfo.md).  
  
     Microsoft SQL Server ve ODBC 2.x koşullarında bir şema sahibi olduğu (örneğin, dbo tipik şema adı'dır). Ayrıca, SQL Server bir tablo kümesini meta verileri depolar: bir tablonun tüm tabloların bir listesini ve başka bir tablo tüm sütunları listesini içerir. Bir Microsoft Access veritabanı şemasında eşdeğeri yoktur.  
  
-   **Tablo** tablolardır belirli bir sırada düzenlenmiş sütunlar koleksiyonu. Verilen katalogda (veritabanı) ve bu tablolar hakkındaki bilgileri tanımlanan tablolarını listelemek için kullanmak [CTables](../../data/oledb/ctables-ctableinfo.md)).  
  
## <a name="restrictions"></a>Kısıtlamalar  
 İçin şema bilgileri sorguladığınızda, ilgilendiğiniz bilgi türünü belirtmek için kısıtlamaları kullanabilirsiniz. Kısıtlama filtre veya sorguda tanımlayıcı olarak düşünebilirsiniz. Örneğin, sorguda:  
  
```  
SELECT * FROM authors where l_name = 'pivo'  
```  
  
 `l_name` bir kısıtlamadır. Bu yalnızca bir kısıtlaması ile çok basit bir örnektir; Şema satır kümesi sınıfları birkaç kısıtlamaları destekler.  
  
 [Şema satır kümesi typedef sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) , diğer bir satır kümesi gibi bir şema satır kümesi başlatmasını ve onu açarak erişebilmesi için tüm OLE DB şema satır kümeleri kapsüller. Örneğin, typedef sınıfı [CColumns](../../data/oledb/ccolumns-ccolumnsinfo.md) olarak tanımlanır:  
  
```  
CRestrictions<CAccessor<CColumnsInfo>  
```  
  
 [CRestrictions](../../data/oledb/crestrictions-class.md) sınıfı kısıtlama desteği sağlar. Şema satır kümesi örneği oluşturduktan sonra arama [CRestrictions::Open](../../data/oledb/crestrictions-open.md). Bu yöntem, belirttiğiniz kısıtlamalara göre bir sonuç kümesi döndürür.  
  
 Kısıtlamaları belirtmek için başvurmak [ek B: şema satır kümeleri](http://go.microsoft.com/fwlink/p/?linkid=64681) ve kullanmakta olduğunuz satır kümesini aratın. Örneğin, **CColumns** karşılık gelen [SÜTUNLARIN satır kümesi](http://go.microsoft.com/fwlink/p/?linkid=64682); Bu konu COLUMNS satır kümesindeki kısıtlama sütunlarını listeler: TABLE_CATALOG, TABLE_SCHEMA, TABLE_NAME, COLUMN_NAME. Bu siparişi, sınırlamaları belirleme izlemeniz gerekir.  
  
 Bu nedenle, örneğin, tablo adı ile kısıtlamak istiyorsanız, TABLE_NAME üçüncü kısıtlama sütunu olduğuna dikkat edin ve ardından arama **açık**, aşağıdaki örnekte gösterildiği gibi üçüncü kısıtlama parametresi olarak istenilen tablo adını belirtme.  
  
#### <a name="to-use-schema-rowsets"></a>Şema satır kümeleri kullanmak için  
  
1.  Üstbilgi dosyası Atldbsch.h içermelidir (kuşkusuz de tüketici desteği Atldbcli.h gerekir).  
  
2.  Bir şema satır kümesi nesnesi tüketicinin veya belgenin üstbilgi dosyası. Tablo bilgileri almak istiyorsanız, bildirme bir **CTables** sütun bilgileri almak istiyorsanız, bildirin; nesnesi bir **CColumns** nesnesi. Bu örnek nasıl yazarlar tablodaki sütunlar alınacağını gösterir:  
  
    ```  
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
  
3.  Bilgiyi getirmek için uygun veri üyesi şema satır kümesi nesnesi, örneğin, erişim `ColumnSchemaRowset.m_szColumnName`. Bu COLUMN_NAME'e karşılık gelir. Her veri üyesi karşılık gelen hangi OLE DB sütununa görmek için bkz: [CColumns](../../data/oledb/ccolumns-ccolumnsinfo.md).  
  
 Şema satır kümesi başvuru için typedef sınıfları sağlanan OLE DB Şablonları (bkz [şema satır kümesi sınıfları ve Typedef sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)).  
  
 Kısıtlama sütunları dahil OLE DB şema satır kümeleri hakkında daha fazla bilgi için bkz: [ek B: şema satır kümeleri](http://go.microsoft.com/fwlink/p/?linkid=64681) OLE DB Programcı Başvurusu.  
  
 Şema satır kümesi sınıfları kullanmayı daha karmaşık örnekleri için bkz: [CatDB](http://msdn.microsoft.com/en-us/003d516b-2bf6-444e-8be5-4ebaa0b66046) ve [DBVIEWER](http://msdn.microsoft.com/en-us/07620f99-c347-4d09-9ebc-2459e8049832) örnekleri.  
  
 Şema satır kümeleri için sağlayıcı desteği hakkında daha fazla bilgi için bkz: [şema satır kümelerini destekleme](../../data/oledb/supporting-schema-rowsets.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Erişimcileri Kullanma](../../data/oledb/using-accessors.md)