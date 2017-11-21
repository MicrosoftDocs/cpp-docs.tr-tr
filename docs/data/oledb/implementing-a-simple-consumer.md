---
title: "Basit Tüketici Uygulama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- clients, creating
- OLE DB consumers, implementing
ms.assetid: 13828167-23a4-4e94-8b6c-878262fda464
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7dc97c0e64558f066250a54098f7316ac8b33076
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="implementing-a-simple-consumer"></a>Basit Tüketici Uygulama
Aşağıdaki konular, basit bir tüketici oluşturmak için MFC Uygulama Sihirbazı'nı ve ATL OLE DB Tüketici Sihirbazı tarafından oluşturulan dosyaların nasıl düzenleneceğini gösterir. Bu örnekte, aşağıdaki bölümleri içerir:  
  
-   "Tüketici verilerle alma" kod bir veritabanı tablosunun tüm veriler satır temelinde okur tüketici uygulama gösterilmektedir.  
  
-   "Tüketiciye ekleme yer işareti desteği" Tüketiciye yer işareti desteği eklemek nasıl gösterir.  
  
-   "Tüketiciye XML desteği ekleme" XML verileri olarak alınan satır kümesi veri çıkışı için tüketici kodunun nasıl değiştirileceğini gösterir.  
  
> [!NOTE]
>  Bu bölümde açıklanan tüketici uygulamasını MyProv ve Provider örnek sağlayıcılarını test etmek için kullanabilirsiniz.  
  
> [!NOTE]
>  MyProv test etmek için bir tüketici uygulama oluşturmak için (aynı sağlayıcı açıklanan [basit salt okunur sağlayıcıyı geliştirme](../../data/oledb/enhancing-the-simple-read-only-provider.md)), "Tüketiciye ekleme yer işareti desteği." bölümünde açıklandığı gibi yer işareti desteği eklemeniz gerekir  
  
> [!NOTE]
>  Sağlayıcı test etmek için bir tüketici uygulama oluşturmak için "Ekleyerek yer işareti desteği tüketiciye içinde" açıklanan yer işareti desteği çıkışı bırakın ve "Tüketiciye ekleme XML desteği." Atla  
  
## <a name="retrieving-data-with-the-consumer"></a>Tüketici ile veri alma  
  
#### <a name="to-modify-the-console-application-to-use-the-ole-db-consumer"></a>OLE DB Tüketici kullanmak için konsol uygulamasını değiştirmek için  
  
1.  MyCons.cpp öğesinde kalın metin şu şekilde ekleyerek ana kodu değiştirin:  
  
    ```  
    // MyCons.cpp : Defines the entry point for the console application.  
    //  
    #include "stdafx.h"  
    #include "Products.h"  
    ...  
    int main(int argc, char* argv[])  
    {  
       HRESULT hr = CoInitialize(NULL);   // Instantiate rowset   CProducts rs;   hr = rs.OpenAll();   ATLASSERT( SUCCEEDED( hr ) );   hr = rs.MoveFirst();   // Iterate through the rowset   while( SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )   {      // Print out the column information for each row      printf("Product ID: %d, Name: %s, Unit Price: %d, Quantity per Unit: %d, Units in Stock %d, Reorder Level %d\n",             rs.m_ProductID, rs.m_ProductName, rs.m_UnitPrice, rs.m_QuantityPerUnit, rs.m_UnitsInStock, rs.m_ReorderLevel );      hr = rs.MoveNext();   }   rs.Close();   rs.ReleaseCommand();   CoUninitialize();  
  
       return 0;  
    }  
    ```  
  
## <a name="adding-bookmark-support-to-the-consumer"></a>Tüketiciye yer işareti desteği ekleme  
 Yer işareti tablosundaki satırları benzersiz olarak tanımlayan bir sütundur. Genellikle anahtar sütunu olduğundan, ancak her zaman; Sağlayıcı özeldir. Bu bölümde yer işareti desteği eklemek nasıl gösterir. Bunu yapmak için kullanıcı kayıt sınıfı aşağıdakileri yapmanız gerekir:  
  
-   Yer işaretleri örneği oluşturur. Nesne türü bunlar [CBookmark](../../data/oledb/cbookmark-class.md).  
  
-   Ayarlayarak sağlayıcıdan bir yer işareti sütun isteği **DBPROP_IRowsetLocate** özelliği.  
  
-   Kullanarak bir yer işareti giriş sütun eşlemesi eklemek [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md) makrosu.  
  
 Önceki adımları yer işareti desteği ve çalışmak bir yer işareti nesnesi sağlar. Bu kod örneği, bir yer işareti gibi gösterir:  
  
-   Yazma için bir dosya açın.  
  
-   Satır kümesi verilerini dosyaya satır temelinde çıktı.  
  
-   Satır kümesi imleci çağırarak yer işaretine taşıma [MoveToBookmark](../../data/oledb/crowset-movetobookmark.md).  
  
-   Çıktı işaretli satır dosyanın sonuna ekleniyor.  
  
> [!NOTE]
>  Bu bölümde açıklanan yer işareti desteği çıkışı sağlayıcısı örnek sağlayıcısı uygulama test etmek için bu tüketici uygulama kullanırsanız bırakın.  
  
#### <a name="to-instantiate-the-bookmark"></a>Yer işareti örneği oluşturmak için  
  
1.  Erişimci türünde bir nesne içermesi gerekir [CBookmark](../../data/oledb/cbookmark-class.md). `nSize` Parametresi yer işareti arabellek boyutu (genellikle 4 32-bit platformları için) ve 64 bit platformları için 8 bayt cinsinden belirtir. Kullanıcı kayıt sınıfı sütun veri üyeleri için aşağıdaki bildirimi ekleyin:  
  
    ```  
    //////////////////////////////////////////////////////////////////////  
    // Products.h  
    class CProductsAccessor  
    {  
    public:  
       CBookmark<4> m_bookmark;   // Add bookmark declaration  
       LONG m_ProductID;  
       ...  
    ```  
  
#### <a name="to-request-a-bookmark-column-from-the-provider"></a>Sağlayıcıdan bir yer işareti sütunu istemek için  
  
1.  Aşağıdaki kodu ekleyin `GetRowsetProperties` kullanıcı kayıt sınıfı yöntemi:  
  
    ```  
    // Set the DBPROP_IRowsetLocate property.  
    void GetRowsetProperties(CDBPropSet* pPropSet)  
    {  
       pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
       pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
       // Add DBPROP_IRowsetLocate property to support bookmarks   pPropSet->AddProperty(DBPROP_IRowsetLocate, true);  
    }  
    ```  
  
#### <a name="to-add-a-bookmark-entry-to-the-column-map"></a>Sütun eşlemesi için bir yer işareti girdisi eklemek için  
  
1.  Kullanıcı kayıt sınıfındaki sütun eşlemesi için şu girdiyi ekleyin:  
  
    ```  
    // Set a bookmark entry in the column map.  
    BEGIN_COLUMN_MAP(CProductsAccessor)  
       BOOKMARK_ENTRY(m_bookmark)   // Add bookmark entry  
       COLUMN_ENTRY_LENGTH_STATUS(1, m_ProductID, m_dwProductIDLength, m_dwProductIDStatus)  
       COLUMN_ENTRY_LENGTH_STATUS(2, m_ProductName, m_dwProductNameLength, m_dwProductNameStatus)  
    ...  
    END_COLUMN_MAP()  
    ```  
  
#### <a name="to-use-a-bookmark-in-your-main-code"></a>Yer işareti ana kodunuzda kullanmak için  
  
1.  Daha önce oluşturduğunuz konsol uygulaması MyCons.cpp dosyasında, aşağıdaki şekilde ana kodu değiştirin. Yer işaretleri kullanmak için ana kodu kendi yer işareti nesne örneği gerekir (`myBookmark`); erişimcisi olandan farklı bir yer işareti budur (`m_bookmark`).  
  
    ```  
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
       while( SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )  
       {  
          nCounter++;  
          if( nCounter == 5 )  
             myBookmark = rs.bookmark;  
          // Output the column information for each row:  
          outfile << rs.m_ProductID << rs.m_ProductName << lPrice << rs.m_QuantityPerUnit << rs.m_UnitsInStock << rs.m_ReorderLevel << endl;  
          hr = rs.MoveNext();  
       }  
  
       // Move cursor to bookmark  
       hr = rs.MoveToBookmark(myBookmark);  
  
       // Iterate through the rowset and output column data to output.txt row by row  
       // In the file, mark the beginning of this set of data:  
       outfile << "row dump starting from bookmarked row" << endl;  
       while( SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )  
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
  
 Yer işaretleri hakkında daha fazla bilgi için bkz: [kullanarak yer işaretleri](../../data/oledb/using-bookmarks.md). Yer işaretleri örnekleri olarak da gösterilir [satır kümelerini güncelleme](../../data/oledb/updating-rowsets.md).  
  
## <a name="adding-xml-support-to-the-consumer"></a>Tüketiciye XML desteği ekleme  
 ' Da anlatıldığı gibi [XML verilerine erişim](../../data/oledb/accessing-xml-data.md), XML verilerini bir veri kaynağından veri almak için iki yolu vardır: kullanarak [CStreamRowset](../../data/oledb/cstreamrowset-class.md) veya kullanarak [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md). Bu örnekte `CStreamRowset`, hangi daha verimli olur, ancak SQL Server 2000'in üzerinde yürütme Bu örnek uygulama bilgisayarda kurulu olmasını gerektirir.  
  
#### <a name="to-modify-the-command-class-to-inherit-from-cstreamrowset"></a>CStreamRowset devralacak şekilde komut sınıfını değiştirmek için  
  
1.  Daha önce oluşturduğunuz tüketici uygulamasında değiştirmek, `CCommand` belirtmek için bildirimi `CStreamRowset` satır kümesi sınıfı şu şekilde:  
  
    ```  
    class CProducts : public CCommand<CAccessor<CProductsAccessor>, CStreamRowset >  
    ```  
  
#### <a name="to-modify-the-main-code-to-retrieve-and-output-the-xml-data"></a>Almak ve çıktı XML verilerini ana kodunu değiştirmek için  
  
1.  Daha önce oluşturduğunuz konsol uygulaması MyCons.cpp dosyasında, aşağıdaki şekilde ana kodu değiştirin:  
  
    ```  
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
  
       // Add variable declarations for the Read method to handle sequential stream data  
       CHAR buffer[1001];  // Pointer to buffer into which data stream is read  
       ULONG cbRead;       // Actual number of bytes read from the data stream  
  
       hr = rs.OpenAll();  
  
       // Open file output.txt for writing in overwrite mode  
       ofstream outfile( "C:\\output.txt", ios::out );  
  
       if (!outfile)      // Test for invalid file  
          return -1;  
  
       // The following loop reads 1000 bytes of the data stream at a time   
       // until it reaches the end of the data stream  
       for (;;)  
       {  
          // Read sequential stream data into buffer  
          HRESULT hr = rs.m_spStream->Read(buffer, 1000, &cbRead);  
          if (FAILED (hr))  
             break;  
          // Output buffer to file  
          buffer[cbRead] = 0;  
          outfile << buffer;  
          // Test for end of data stream  
          if (cbRead < 1000)  
             break;  
       }  
  
       rs.CloseAll();  
       CoUninitialize();  
  
       return 0;  
    }  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sihirbaz kullanarak bir OLE DB Tüketicisi Oluşturma](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)