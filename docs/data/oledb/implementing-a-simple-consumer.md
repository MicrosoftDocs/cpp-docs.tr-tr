---
title: Basit Tüketici Uygulama
ms.date: 08/19/2019
helpviewer_keywords:
- OLE DB consumers, implementing
ms.assetid: 13828167-23a4-4e94-8b6c-878262fda464
ms.openlocfilehash: 9e93b40313a215dfe5872b33dc7d41641204a2f1
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91508978"
---
# <a name="implementing-a-simple-consumer"></a>Basit Tüketici Uygulama

::: moniker range="vs-2019"

ATL OLE DB Tüketici Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz. İşlevselliği el ile de ekleyebilirsiniz. Daha fazla bilgi için bkz. [Sihirbaz kullanmadan tüketici oluşturma](creating-a-consumer-without-using-a-wizard.md).

::: moniker-end

::: moniker range="<=vs-2017"

Aşağıdaki konularda, basit bir tüketici oluşturmak için **MFC Uygulama Sihirbazı** ve **ATL OLE DB Tüketici Sihirbazı** tarafından oluşturulan dosyaların nasıl düzenleneceği gösterilmektedir. Bu örnek aşağıdaki bölümlere sahiptir:

- [Tüketiciyle veri alma](#retrieve) , bir veritabanı tablosundan tüm verileri, satırları satıra göre okuyan tüketicideki kodun nasıl uygulanacağını gösterir.

- [Tüketiciye yer Işareti desteği eklemek,](#bookmark) tüketiciye nasıl yer işareti desteğinin ekleneceğini gösterir.

> [!NOTE]
> Bu bölümde açıklanan Tüketici uygulamasını, `MyProv` ve örnek sağlayıcıları test etmek için kullanabilirsiniz `Provider` .

> [!NOTE]
> Sınanacak bir tüketici uygulaması oluşturmak için `MyProv` ( [basit salt okuma sağlayıcısını geliştirme](../../data/oledb/enhancing-the-simple-read-only-provider.md)bölümünde açıklanan sağlayıcı), [tüketiciye yer işareti desteği ekleme](#bookmark)bölümünde açıklandığı gibi yer işareti desteği eklemeniz gerekir.

## <a name="retrieving-data-with-the-consumer"></a><a name="retrieve" ></a> Tüketiciyle veri alma

### <a name="to-modify-the-console-application-to-use-the-ole-db-consumer"></a>Konsol uygulamasını OLE DB tüketicisini kullanacak şekilde değiştirmek için

1. İçinde `MyCons.cpp` , aşağıdaki gibi kalın metni ekleyerek ana kodu değiştirin:

    ```cpp
    // MyCons.cpp : Defines the entry point for the console application.
    //
    #include "pch.h" // "stdafx.h" in Visual Studio 2017 and earlier
    #include "Products.h"
    ...
    int main(int argc, char* argv[])
    {
       HRESULT hr = CoInitialize(NULL);   // Instantiate rowset
       CProducts rs;
       hr = rs.OpenAll();
       ATLASSERT(SUCCEEDED(hr ) );
       hr = rs.MoveFirst();   // Iterate through the rowset
       while(SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )   {      // Print out the column information for each row
         printf("Product ID: %d, Name: %s, Unit Price: %d, Quantity per Unit: %d, Units in Stock %d, Reorder Level %d\n",
           rs.m_ProductID, rs.m_ProductName, rs.m_UnitPrice, rs.m_QuantityPerUnit, rs.m_UnitsInStock, rs.m_ReorderLevel );
         hr = rs.MoveNext();   }
       rs.Close();
       rs.ReleaseCommand();
       CoUninitialize();

       return 0;
    }
    ```

## <a name="adding-bookmark-support-to-the-consumer"></a><a name="bookmark" ></a> Tüketiciye yer Işareti desteği ekleme

Yer işareti, tablodaki satırları benzersiz bir şekilde tanımlayan bir sütundur. Genellikle bu, anahtar sütundur, ancak her zaman değildir; sağlayıcıya özeldir. Bu bölüm, yer işareti desteğinin nasıl ekleneceğini gösterir. Bunu yapmak için, Kullanıcı kayıt sınıfında aşağıdaki adımları gerçekleştirmeniz gerekir:

- Yer işaretlerinin örneğini oluşturun. Bunlar [CBookmark](../../data/oledb/cbookmark-class.md)türünde nesnelerdir.

- Özelliği ayarlayarak sağlayıcıdan bir yer işareti sütunu isteyin `DBPROP_IRowsetLocate` .

- [BOOKMARK_ENTRY](./macros-and-global-functions-for-ole-db-consumer-templates.md#bookmark_entry) makrosunu kullanarak sütun haritasına bir yer işareti girişi ekleyin.

Önceki adımlarda, yer işareti desteği ve çalışmak için bir yer işareti nesnesi vardır. Bu kod örneği, bir yer işaretini aşağıdaki gibi gösterir:

- Yazmak için bir dosya açın.

- Satır kümesi verilerini satıra göre dosya satırına çıktı.

- [MoveToBookmark](./crowset-class.md#movetobookmark)öğesini çağırarak satır kümesi imlecini yer işaretine taşıyın.

- Yer işareti eklenecek satırı, dosyanın sonuna ekleyerek çıkış.

> [!NOTE]
> Örnek sağlayıcı uygulamasını test etmek için bu tüketici uygulamasını kullanırsanız `Provider` , bu bölümde açıklanan yer işareti desteğini bırakın.

### <a name="to-instantiate-the-bookmark"></a>Yer işaretinin örneğini oluşturmak için

1. Erişimcinin [CBookmark](../../data/oledb/cbookmark-class.md)türünde bir nesneyi tutması gerekir. *NSize* parametresi, yer işareti arabelleğinin bayt cinsinden boyutunu belirtir (32 bitlik platformlar için 4 ve 64 bit platformlar için 8). Aşağıdaki bildirimi, Kullanıcı kaydı sınıfındaki sütun veri üyelerine ekleyin:

    ```cpp
    //////////////////////////////////////////////////////////////////////
    // Products.h
    class CProductsAccessor
    {
    public:
       CBookmark<4> m_bookmark;   // Add bookmark declaration
       LONG m_ProductID;
       ...
    ```

### <a name="to-request-a-bookmark-column-from-the-provider"></a>Sağlayıcıdan bir yer işareti sütunu istemek için

1. Aşağıdaki kodu, `GetRowsetProperties` Kullanıcı kaydı sınıfındaki yöntemine ekleyin:

    ```cpp
    // Set the DBPROP_IRowsetLocate property.
    void GetRowsetProperties(CDBPropSet* pPropSet)
    {
       pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
       pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
       // Add DBPROP_IRowsetLocate property to support bookmarks   pPropSet->AddProperty(DBPROP_IRowsetLocate, true);
    }
    ```

### <a name="to-add-a-bookmark-entry-to-the-column-map"></a>Sütun eşlemesine bir yer işareti girdisi eklemek için

1. Aşağıdaki girişi, Kullanıcı kaydı sınıfındaki sütun haritasına ekleyin:

    ```cpp
    // Set a bookmark entry in the column map.
    BEGIN_COLUMN_MAP(CProductsAccessor)
       BOOKMARK_ENTRY(m_bookmark)   // Add bookmark entry
       COLUMN_ENTRY_LENGTH_STATUS(1, m_ProductID, m_dwProductIDLength, m_dwProductIDStatus)
       COLUMN_ENTRY_LENGTH_STATUS(2, m_ProductName, m_dwProductNameLength, m_dwProductNameStatus)
    ...
    END_COLUMN_MAP()
    ```

### <a name="to-use-a-bookmark-in-your-main-code"></a>Ana kodunuzda bir yer işareti kullanmak için

1. `MyCons.cpp`Daha önce oluşturduğunuz konsol uygulamasındaki dosyada, ana kodu aşağıdaki gibi okunacak şekilde değiştirin. Yer işaretlerini kullanmak için ana kodun kendi yer işareti nesnesinin () örneği oluşturması gerekir `myBookmark` ; Bu, erişimcinin () içinden farklı bir yer işaretidir `m_bookmark` .

    ```cpp
    ///////////////////////////////////////////////////////////////////////
    // MyCons.cpp : Defines the entry point for the console application.
    //

    #include "stdafx.h"
    #include "Products.h"
    #include <iostream>
    #include <fstream>
    using namespace std;

    int _tmain(int argc, _TCHAR* argv[])
    {
       HRESULT hr = CoInitialize(NULL);

       // Instantiate rowset
       CProducts rs;

       hr = rs.OpenAll();
       hr = rs.MoveFirst();

       // Cast CURRENCY m_UnitPrice to a long value
       LONGLONG lPrice = rs.m_UnitPrice.int64;

       // Open file output.txt for writing in overwrite mode
       ofstream outfile( "C:\\output.txt", ios::out );

       if (!outfile)      // Test for invalid file
          return -1;

       // Instantiate a bookmark object myBookmark for the main code
       CBookmark<4> myBookmark;
       int nCounter = 0;

       // Iterate through the rowset and output column data to output.txt row by row
       // In the file, mark the beginning of this set of data:
       outfile << "initial row dump" << endl;
       while(SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )
       {
          nCounter++;
          if(nCounter == 5 )
             myBookmark = rs.m_bookmark;
          // Output the column information for each row:
          outfile << rs.m_ProductID << rs.m_ProductName << lPrice << rs.m_QuantityPerUnit << rs.m_UnitsInStock << rs.m_ReorderLevel << endl;
          hr = rs.MoveNext();
       }

       // Move cursor to bookmark
       hr = rs.MoveToBookmark(myBookmark);

       // Iterate through the rowset and output column data to output.txt row by row
       // In the file, mark the beginning of this set of data:
       outfile << "row dump starting from bookmarked row" << endl;
       while(SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )
       {
          // Output the column information for each row
          outfile << rs.m_ProductID << rs.m_ProductName << lPrice << rs.m_QuantityPerUnit << rs.m_UnitsInStock << rs.m_ReorderLevel << endl;
          hr = rs.MoveNext();
       }

       rs.CloseAll();
       CoUninitialize();

       return 0;
    }
    ```

Yer işaretleri hakkında daha fazla bilgi için bkz. [yer Imlerini kullanma](../../data/oledb/using-bookmarks.md). [Satır kümelerini güncelleştirme](../../data/oledb/updating-rowsets.md)bölümünde ayrıca yer işaretleri örnekleri gösterilir.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[Sihirbaz kullanarak OLE DB tüketicisi oluşturma](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)
