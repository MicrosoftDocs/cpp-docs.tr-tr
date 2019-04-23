---
title: Basit Tüketici Uygulama
ms.date: 10/12/2018
helpviewer_keywords:
- clients, creating
- OLE DB consumers, implementing
ms.assetid: 13828167-23a4-4e94-8b6c-878262fda464
ms.openlocfilehash: 9067e8645fac9a06bd85ca5ef18fbaff45d16aae
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59033540"
---
# <a name="implementing-a-simple-consumer"></a>Basit Tüketici Uygulama

Aşağıdaki konular tarafından oluşturulan dosyaların nasıl düzenleneceğini gösterir **MFC Uygulama Sihirbazı** ve **ATL OLE DB Tüketicisi Sihirbazı** Basit Tüketici oluşturma. Bu örnek aşağıdaki bölümleri içerir:

- [Tüketici ile veri alma](#retrieve) nasıl tüm veriler satır temelinde bir veritabanı tablosundan okur tüketicide kod uygulanacağı gösterilmektedir.

- [Yer işareti desteği ekleme tüketiciye](#bookmark) tüketiciye yer işareti desteği ekleme işlemi gösterilmektedir.

> [!NOTE]
> Bu bölümde açıklanan tüketici uygulama test etmek için kullanabileceğiniz `MyProv` ve `Provider` örnek sağlayıcıları.

> [!NOTE]
> Test etmek için bir tüketici uygulama oluşturmak için `MyProv` (aynı sağlayıcının açıklanan [basit salt okunur sağlayıcıyı geliştirme](../../data/oledb/enhancing-the-simple-read-only-provider.md)), yer işareti desteği açıklandığı içermelidir [için yer işareti desteği ekleme Tüketici](#bookmark).

## <a name="retrieve" ></a> Tüketici ile veri alma

### <a name="to-modify-the-console-application-to-use-the-ole-db-consumer"></a>OLE DB Tüketici kullanmak için konsol uygulamasını değiştirmek için

1. İçinde `MyCons.cpp`, kalın metin gibi ekleyerek ana kodu değiştirin:

    ```cpp
    // MyCons.cpp : Defines the entry point for the console application.
    //
    #include "stdafx.h"
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

## <a name="bookmark" ></a> Tüketiciye yer işareti desteği ekleme

Bir yer işareti tablosundaki satırları benzersiz olarak tanımlayan bir sütundur. Genellikle, anahtar sütunu olduğundan ama her zaman kullanılmaz; Sağlayıcı özeldir. Bu bölümde yer işareti desteğini nasıl ekleyeceğinizi gösterir. Bunu yapmak için kullanıcı kayıt sınıfı aşağıdakileri yapmanız gerekir:

- Yer işaretleri örneği oluşturur. Türündeki nesneler bunlar [CBookmark](../../data/oledb/cbookmark-class.md).

- Ayarlayarak sağlayıcısından yer işareti sütunu istek `DBPROP_IRowsetLocate` özelliği.

- Kullanarak bir yer işareti girişi için sütun eşlemesi eklemek [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md) makrosu.

Önceki adımları yer işareti desteği ve çalışmak için yer imi nesneyle verin. Bu kod örneği, bir yer işareti gibi gösterir:

- Yazma için bir dosya açın.

- Satır kümesi veri dosyasına satır satır çıktı.

- Satır kümesi imleci çağırarak yer işaretine Taşı [MoveToBookmark](../../data/oledb/crowset-movetobookmark.md).

- Çıkış işaretli satır, dosyanın sonuna ekleniyor.

> [!NOTE]
> Test etmek için bu tüketici uygulama kullanırsanız `Provider` örnek sağlayıcısı uygulaması, bu bölümde açıklanan yer işareti desteği bırakın.

### <a name="to-instantiate-the-bookmark"></a>Yer işareti oluşturmak için

1. Erişimci türünde bir nesne tutmak gereken [CBookmark](../../data/oledb/cbookmark-class.md). *NSize* parametresi yer işareti arabellek boyutu (genellikle 32 bit platformları için 4) ve 64-bit platformları için 8 bayt cinsinden belirtir. Sütun veri üyeleri kullanıcı kaydı sınıfında aşağıdaki bildirimi ekleyin:

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

### <a name="to-request-a-bookmark-column-from-the-provider"></a>Bir yer işareti sütunu Sağlayıcısı'ndan istemek için

1. Aşağıdaki kodu ekleyin `GetRowsetProperties` kullanıcı kayıt sınıfı yöntemi:

    ```cpp
    // Set the DBPROP_IRowsetLocate property.
    void GetRowsetProperties(CDBPropSet* pPropSet)
    {
       pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
       pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
       // Add DBPROP_IRowsetLocate property to support bookmarks   pPropSet->AddProperty(DBPROP_IRowsetLocate, true);
    }
    ```

### <a name="to-add-a-bookmark-entry-to-the-column-map"></a>Sütun eşlemesi için bir yer işareti giriş eklemek için

1. Kullanıcı kayıt sınıfı sütun eşlemesinde şu girişi ekleyin:

    ```cpp
    // Set a bookmark entry in the column map.
    BEGIN_COLUMN_MAP(CProductsAccessor)
       BOOKMARK_ENTRY(m_bookmark)   // Add bookmark entry
       COLUMN_ENTRY_LENGTH_STATUS(1, m_ProductID, m_dwProductIDLength, m_dwProductIDStatus)
       COLUMN_ENTRY_LENGTH_STATUS(2, m_ProductName, m_dwProductNameLength, m_dwProductNameStatus)
    ...
    END_COLUMN_MAP()
    ```

### <a name="to-use-a-bookmark-in-your-main-code"></a>Bir yer işareti ana kodunuzda kullanmak için

1. İçinde `MyCons.cpp` dosyasından daha önce oluşturduğunuz, değiştirdiğiniz gibi görünecek şekilde ana kod konsol uygulaması. Yer işaretlerini kullanmak için kendi yer işareti nesnesi örneklemek ana kod gerekir (`myBookmark`); bu erişimcisindeki olandan farklı bir yer işareti, (`m_bookmark`).

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

Yer işaretleri hakkında daha fazla bilgi için bkz. [kullanarak yer işaretleri](../../data/oledb/using-bookmarks.md). Yer işaretleri örnekleri de gösterilir [satır kümelerini güncelleştirme](../../data/oledb/updating-rowsets.md).

## <a name="see-also"></a>Ayrıca bkz.

[Sihirbaz Kullanarak bir OLE DB Tüketicisi Oluşturma](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)
