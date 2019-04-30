---
title: Sihirbazın Ürettiği Erişimcilerde Alan Durumu Veri Üyeleri
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB consumer templates, field status
- field status in OLE DB templates
ms.assetid: 66e4e223-c60c-471e-860d-d23abcdfe371
ms.openlocfilehash: dd650b7cafef78e23c23ddfef791c88b6b93727f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409011"
---
# <a name="field-status-data-members-in-wizard-generated-accessors"></a>Sihirbazın Ürettiği Erişimcilerde Alan Durumu Veri Üyeleri

Kullanırken **ATL OLE DB Tüketicisi Sihirbazı** bir tüketici oluşturmak için sütun eşlemesinde belirttiğiniz her bir alan için kullanıcı kayıt sınıftaki veri üyesi sihirbaz oluşturur. Her veri üyesi türünde `DWORD` ve kendi ilgili alana karşılık gelen bir durum değeri içerir.

Örneğin, bir veri üyesi için *m_OwnerID*, alan durumu için bir ek veri üyesi sihirbaz oluşturur (*dwOwnerIDStatus*) ve başka bir alan uzunluğu için (*dwOwnerIDLength*). Ayrıca, bir sütun eşlemesi COLUMN_ENTRY_LENGTH_STATUS girişi oluşturur.

Bu, aşağıdaki kodda gösterilmiştir:

```cpp
class CAuthorsAccessor
{
public:
   LONG m_AuID;
   TCHAR m_Author[53];
   LONG m_YearBorn;

   DBSTATUS m_dwAuIDStatus;
   DBSTATUS m_dwAuthorStatus;
   DBSTATUS m_dwYearBornStatus;

   DBLENGTH m_dwAuIDLength;
   DBLENGTH m_dwAuthorLength;
   DBLENGTH m_dwYearBornLength;

    DEFINE_COMMAND_EX(CAuthorsAccessor, L" \
    SELECT \
        AuID, \
        Author, \
        YearBorn \
        FROM dbo.Authors")

    BEGIN_COLUMN_MAP(CAuthorsAccessor)
       COLUMN_ENTRY_LENGTH_STATUS(1, m_AuID, dwAuIDLength, dwAuIDStatus)
       COLUMN_ENTRY_LENGTH_STATUS(2, m_Author, dwAuthorLength, dwAuthorStatus)
       COLUMN_ENTRY_LENGTH_STATUS(3, m_YearBorn, dwYearBornLength, dwYearBornStatus)
    END_COLUMN_MAP()
...
```

> [!NOTE]
> Kullanıcı kayıt sınıfı değiştirin ya da kendi tüketici yazma, verileri değişkenleri durum ve uzunluğu değişkenlerinden önce gelmelidir.

Hata ayıklama amacıyla durum değerleri kullanabilirsiniz. Kod tarafından oluşturulan, **ATL OLE DB Tüketicisi Sihirbazı** derleme hatası veriyorsa DB_S_ERRORSOCCURRED veya DB_E_ERRORSOCCURRED gibi alan durumu veri üyeleri, geçerli değerlere önce görünmelidir. Sıfır olmayan değerler sahip olanlar sorunlu sütunlara karşılık gelir.

Durum değerleri, belirli bir alan için bir NULL değer ayarlamak için de kullanabilirsiniz. Bunun yapılması, bir alan değeri sıfır yerine NULL olarak ayırmak istediğiniz durumlarda yardımcı olur. Bu NULL geçerli bir değer veya özel bir değeri olup olmadığına karar vermenize ve uygulamanızı bunu nasıl işleyeceğini karar size bağlıdır. OLE DB DBSTATUS_S_ISNULL genel bir NULL değer belirtme doğru şekilde tanımlar. Tüketici verileri okur ve değer null ise, Durum alanını DBSTATUS_S_ISNULL ayarlanır. Bir NULL değer ayarlamak tüketici isterse, tüketici sağlayıcı çağırmadan önce DBSTATUS_S_ISNULL durum değeri ayarlar.

Ardından, biçim ve DBSTATUSENUM araması açın. Ardından, sıfır olmayan durum DBSTATUSENUM numaralandırma değerlerinden karşı sayısal değerini eşleşebilir. Sabit listesi adı bakın, neyin yanlış olduğunu söylemek için yeterli değilse **durumu** konudaki **bağlama veri değerleri** bölümünü [OLE DB Programcı Kılavuzu](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming). Bu konu, veri alma veya ayarlarken kullanılan durum değerleri tabloları içerir. Uzunluk değerleri hakkında daha fazla bilgi için bkz: **uzunluğu** aynı bölüme konu.

## <a name="retrieving-the-length-or-status-of-a-column"></a>Uzunluk veya bir sütun durumunu alma

Bir değişken uzunluklu sütun uzunluğu ya da bir sütun (DBSTATUS_S_ISNULL için örneğin denetlemek için) durumunu alabilirsiniz:

- Uzunluğu almak için COLUMN_ENTRY_LENGTH makrosu kullanın.

- Durumu almak için COLUMN_ENTRY_STATUS makrosu kullanın.

- Her ikisini de almak için COLUMN_ENTRY_LENGTH_STATUS, gösterildiği gibi kullanın:

    ```cpp
    class CProducts
    {
    public:
       char      szName[40];
       long      nNameLength;
       DBSTATUS   nNameStatus;

    BEGIN_COLUMN_MAP(CProducts)
    // Bind the column to CProducts.m_ProductName.
    // nOrdinal is zero-based, so the column number of m_ProductName is 1.
       COLUMN_ENTRY_LENGTH_STATUS(1, szName, nNameLength, nNameStatus)
    END_COLUMN_MAP()
    };
    ```

- Ardından, uzunluğu ve/veya durum gösterildiği gibi erişebilirsiniz:

    ```cpp
    CTable<CAccessor<CProducts >> product;
    CSession session;

    product.Open(session, "Product");

    while (product.MoveNext() == S_OK)
    {
       // Check the product name isn't NULL before tracing it
       if (product.nNameStatus == DBSTATUS_S_OK)
          ATLTRACE("%s is %d characters\n", product.szName, product.nNameLength);
    }
    ```

Kullanırken `CDynamicAccessor`, uzunluğu ve durum sizin için otomatik olarak bağlanır. Uzunluğu ve durum değerleri almak için kullanın `GetLength` ve `GetStatus` üye işlevleri.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketici Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-consumer-templates.md)