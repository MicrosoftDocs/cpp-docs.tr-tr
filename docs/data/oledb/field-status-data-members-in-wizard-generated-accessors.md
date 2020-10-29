---
title: Sihirbazın Ürettiği Erişimcilerde Alan Durumu Veri Üyeleri
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB consumer templates, field status
- field status in OLE DB templates
ms.assetid: 66e4e223-c60c-471e-860d-d23abcdfe371
ms.openlocfilehash: 476c91f55071f6d1c7f243257273a32798813cae
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924642"
---
# <a name="field-status-data-members-in-wizard-generated-accessors"></a>Sihirbazın Ürettiği Erişimcilerde Alan Durumu Veri Üyeleri

::: moniker range="msvc-160"

ATL OLE DB Tüketici Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz. İşlevselliği el ile de ekleyebilirsiniz. Daha fazla bilgi için bkz. [Sihirbaz kullanmadan tüketici oluşturma](creating-a-consumer-without-using-a-wizard.md).

::: moniker-end

::: moniker range="<=msvc-150"

Bir tüketici oluşturmak için **ATL OLE DB Tüketici Sihirbazı** 'nı kullandığınızda, sihirbaz, sütun haritanızda belirttiğiniz her alan için Kullanıcı kayıt sınıfında bir veri üyesi oluşturur. Her veri üyesi türüdür `DWORD` ve ilgili alanına karşılık gelen bir durum değeri içerir.

Örneğin, bir veri üyesi *m_OwnerID* için, sihirbaz alan durumu ( *dwOwnerIDStatus* ) için ek bir veri üyesi ve alan uzunluğu ( *dwOwnerIDLength* ) için başka bir tane oluşturur. Ayrıca, COLUMN_ENTRY_LENGTH_STATUS girdileri olan bir sütun haritası da oluşturur.

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
> Kullanıcı kayıt sınıfını değiştirir veya kendi tüketicinizi yazarsanız, veri değişkenlerinin durum ve uzunluk değişkenlerinden önce gelmesi gerekir.

Hata ayıklama amacıyla durum değerlerini kullanabilirsiniz. **ATL OLE DB Tüketici Sihirbazı** tarafından oluşturulan kod DB_S_ERRORSOCCURRED veya db_e_errorsoccurred gibi derleme hataları oluşturursa, önce alan durumu veri üyelerinin geçerli değerlerine bakmanız gerekir. Sıfır olmayan değerlere sahip olanlar, sorunlu sütunlara karşılık gelir.

Ayrıca, belirli bir alan için NULL değer ayarlamak üzere durum değerlerini de kullanabilirsiniz. Bunun yapılması, alan değerini sıfır yerine NULL olarak ayırmak istediğiniz durumlarda size yardımcı olur. NULL değerinin geçerli bir değer mi yoksa özel bir değer mi olduğunu ve uygulamanızın onu nasıl işleyeceğine karar vermek sizin için. OLE DB, genel bir NULL değeri belirtmenin doğru yolu olarak DBSTATUS_S_ISNULL tanımlar. Tüketici verileri okur ve değer null ise, durum alanı DBSTATUS_S_ISNULL olarak ayarlanır. Tüketici NULL değer ayarlamak istiyorsa, sağlayıcı çağrılmadan önce, tüketici durum değerini DBSTATUS_S_ISNULL olarak ayarlar.

Sonra, OLEDB. h ' yi açın ve DBSTATUSENUM araması yapın. Bundan sonra, sıfır dışında durumunun sayısal değerini DBSTATUSENUM numaralandırma değerleriyle eşleştirebilirsiniz. Numaralandırma adı neyin yanlış olduğunu söylemek için yeterli değilse, [OLE DB Programcı kılavuzunun](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming) **veri değerleri bağlama** bölümünde **durum** konusuna bakın. Bu konu, verileri alırken veya ayarlarken kullanılan durum değerlerinin tablolarını içerir. Uzunluk değerleri hakkında daha fazla bilgi için aynı bölümdeki **uzunluk** konusuna bakın.

## <a name="retrieving-the-length-or-status-of-a-column"></a>Bir sütunun uzunluğunu veya durumunu alma

Değişken uzunluklu bir sütunun uzunluğunu veya bir sütunun durumunu alabilirsiniz (örneğin, DBSTATUS_S_ISNULL denetlemek için):

- Uzunluğu almak için COLUMN_ENTRY_LENGTH makrosunu kullanın.

- Durumu almak için COLUMN_ENTRY_STATUS makrosunu kullanın.

- Her ikisini de almak için, gösterildiği gibi COLUMN_ENTRY_LENGTH_STATUS kullanın:

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

- Ardından, belirtilen uzunluğa ve/veya duruma şu şekilde erişin:

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

Kullandığınızda `CDynamicAccessor` , uzunluk ve durum sizin için otomatik olarak bağlanır. Uzunluk ve durum değerlerini almak için, `GetLength` ve `GetStatus` üye işlevlerini kullanın.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonlarıyla çalışma](../../data/oledb/working-with-ole-db-consumer-templates.md)
