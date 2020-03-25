---
title: Şema Satır Kümeleri ile Meta Verileri Alma
ms.date: 10/24/2018
helpviewer_keywords:
- schema rowsets, getting OLE DB provider metadata
- OLE DB consumer templates, getting provider metadata
- metadata, getting (OLE DB Templates)
ms.assetid: 6b448461-82fb-4acf-816b-3cbb0ca1d186
ms.openlocfilehash: e04b9a335c60cefdc28be2347ef1f0762c424d8e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210138"
---
# <a name="obtaining-metadata-with-schema-rowsets"></a>Şema Satır Kümeleri ile Meta Verileri Alma

Bazen, satır kümesini açmadan sağlayıcı, satır kümesi, tablo, sütun veya diğer veritabanı bilgileri hakkında bilgi almanız gerekir. Veritabanı yapısıyla ilgili verilere meta veriler denir ve birçok farklı yöntem tarafından alınabilir. Bir yöntem, şema satır kümelerini kullanmaktır.

OLE DB şablonlar, şema bilgilerini almak için bir sınıf kümesi sağlar; Bu sınıflar önceden tanımlanmış şema satır kümeleri oluşturur ve [şema satır kümesi sınıfları ve typedef sınıflarında](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)listelenmiştir.

> [!NOTE]
> OLAP kullanıyorsanız ve bazı satır kümeleriniz şema satır kümesi sınıfları tarafından desteklenmiyorsa (örneğin, değişken sayıda sütunlarınız varsa) `CManualAccessor` veya `CDynamicAccessor`kullanmayı düşünmelisiniz. Her sütun için olası veri türlerini işlemek için sütunlar ve kullanım örneği deyimleriyle gezinebilirsiniz.

## <a name="catalogschema-model"></a>Katalog/şema modeli

ANSI SQL, veri depoları için bir katalog/şema modeli tanımlar; OLE DB bu modeli kullanır. Bu modelde, katalogların (veritabanları) şemaları ve şemaları tabloları vardır.

- **Katalog** Bir katalog, bir veritabanı için başka bir addır. Bu bir ilişkili şemalar koleksiyonudur. Belirli bir veri kaynağına ait katalogları (veritabanları) listelemek için [CCatalog](../../data/oledb/ccatalogs-ccataloginfo.md)kullanın. Birçok veritabanının yalnızca bir kataloğu olduğundan meta veriler bazen şema bilgisi olarak adlandırılır.

- **Şema** Şema, belirli bir kullanıcı tarafından sahip olunan veya oluşturulmuş bir veritabanı nesneleri koleksiyonudur. Belirli bir kullanıcının sahip olduğu şemaları listelemek için [CSchemata](../../data/oledb/cschemata-cschematainfo.md)kullanın.

   Microsoft SQL Server ve ODBC 2. x koşullarında, bir şema sahipdir (örneğin, dbo tipik bir şema adıdır). Ayrıca, SQL Server meta verileri bir tablo kümesinde depolar: bir tablo, tüm tabloların bir listesini içerir ve başka bir tablo, tüm sütunların bir listesini içerir. Bir Microsoft Access veritabanındaki şemayla eşdeğer değildir.

- **Tablo** Tablolar, belirli siparişlerde düzenlenmiş sütunların koleksiyonlarıdır. Belirli bir katalogda (veritabanı) tanımlanan tabloları ve bu tablolar hakkındaki bilgileri listelemek için [CTables](../../data/oledb/ctables-ctableinfo.md)' ı kullanın.

## <a name="restrictions"></a>Kısıtlamalar

Şema bilgilerini Sorgulayabileceğiniz zaman, ilgilendiğiniz bilgi türünü belirtmek için kısıtlamaları kullanabilirsiniz. Kısıtlamaları sorguda filtre veya niteleyici olarak düşünebilirsiniz. Örneğin, sorgusunda:

```sql
SELECT * FROM authors WHERE l_name = 'pivo'
```

`l_name` bir kısıtlamadır. Tek bir kısıtlamaya sahip basit bir örnektir; şema satır kümesi sınıfları çeşitli kısıtlamaları destekler.

Şema satır [kümesi typedef sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) , tüm OLE DB şema satır kümelerini kapsülleyerek, örneği oluşturarak ve açarak bir şema satır kümesine tıpkı benzer bir satır kümesi gibi erişebilirsiniz. Örneğin, [CColumns](../../data/oledb/ccolumns-ccolumnsinfo.md) typedef sınıfı şu şekilde tanımlanır:

```cpp
CRestrictions<CAccessor<CColumnsInfo>
```

[CRestrictions](../../data/oledb/crestrictions-class.md) sınıfı kısıtlama desteğini sağlar. Şema satır kümesi örneğini oluşturduktan sonra, [CRestrictions:: Open](../../data/oledb/crestrictions-open.md)çağrısı yapın. Bu yöntem, belirttiğiniz kısıtlamalara göre bir sonuç kümesi döndürür.

Kısıtlamaları belirtmek için [Ek B: şema satır kümeleri](/previous-versions/windows/desktop/ms712921(v=vs.85)) ' ne bakın ve kullanmakta olduğunuz satır kümesini bulun. Örneğin, `CColumns` [sütunları satır kümesine](/previous-versions/windows/desktop/ms723052(v=vs.85))karşılık gelir; Bu konuda, sütun satır kümesindeki kısıtlama sütunları listelenmektedir: TABLE_CATALOG, TABLE_SCHEMA, TABLE_NAME COLUMN_NAME. Kısıtlamalarınızı belirtirken bu sırayı izlemeniz gerekir.

Bu nedenle, örneğin, tablo adına göre kısıtlamak istiyorsanız, üçüncü kısıtlama sütunudur TABLE_NAME ve ardından, aşağıdaki örnekte gösterildiği gibi, istenen tablo adını üçüncü kısıtlama parametresi olarak belirterek `Open`çağırın.

### <a name="to-use-schema-rowsets"></a>Şema satır kümelerini kullanmak için

1. Üst bilgi dosyası `Atldbsch.h` ekleyin (tüketici desteğinin yanı sıra `Atldbcli.h` gerekir).

1. Tüketicinin veya belgenin başlık dosyasında bir şema satır kümesi nesnesi örneği oluşturun. Tablo bilgilerini isterseniz, `CTables` nesnesi bildirin; sütun bilgilerini isterseniz, bir `CColumns` nesnesi bildirin. Bu örnek, yazarlar tablosundaki sütunların nasıl alınacağını gösterir:

    ```cpp
    CDataSource ds;
    ds.Open();
    CSession ss;
    ss.Open(ds);
    CColumns columnSchemaRowset;
    // TABLE_NAME is the third restriction column, so
    // specify "authors" as the third restriction parameter:
    HRESULT hr = columnSchemaRowset.Open(ss, NULL, NULL, L"authors");
    hr = columnSchemaRowset.MoveFirst();
    while (hr == S_OK)
    {
       hr = columnSchemaRowset.MoveNext();
    }
    ```

1. Bilgileri getirmek için, şema satır kümesi nesnesinin uygun veri üyesine erişin, örneğin `ColumnSchemaRowset.m_szColumnName`. Bu veri üyesi COLUMN_NAME karşılık gelir. Her veri üyesine karşılık gelen OLE DB sütununu görmek için bkz. [CColumns](../../data/oledb/ccolumns-ccolumnsinfo.md).

Şema satır kümesi başvurusu için OLE DB şablonlarda belirtilen typedef sınıfları (bkz. [şema satır kümesi sınıfları ve typedef sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)).

Kısıtlama sütunları dahil OLE DB şema satır kümeleri hakkında daha fazla bilgi için, bkz. [Ek B: şema satır kümeleri](/previous-versions/windows/desktop/ms712921(v=vs.85)) **OLE DB Programcı başvurusu**.

Şema satır kümesi sınıflarının nasıl kullanılacağına ilişkin daha karmaşık örnekler için, [CATDB](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Consumer) ve [DBViewer](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Consumer) örneklerine bakın.

Şema satır kümeleri için sağlayıcı desteği hakkında daha fazla bilgi için bkz. [şema satır kümelerini destekleme](../../data/oledb/supporting-schema-rowsets.md).

## <a name="see-also"></a>Ayrıca bkz.

[Erişimcileri Kullanma](../../data/oledb/using-accessors.md)
