---
title: "Dinamik Erişimcileri Kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- accessors [C++], dynamic
- dynamic accessors
ms.assetid: e5d5bfa6-2b1d-49d0-8ced-914666422431
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b3d2e722ce96ff7a2f1add779377079a0eaecfc6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="using-dynamic-accessors"></a>Dinamik Erişimcileri Kullanma
Dinamik erişimciler veritabanı şeması (temel yapısı) olanağıyla varsa, bir veri kaynağına erişmek sağlar. OLE DB şablonları kitaplığı, bu yapmanıza yardımcı olmak için çeşitli sınıflar sağlar.  
  
 [DynamicConsumer](http://msdn.microsoft.com/en-us/2ccc4c61-6749-4e83-aa81-00f8009c0dc3) örnek dinamik erişimciyi sınıfları sütun bilgi edinebilir ve dinamik olarak erişimciler oluşturmak için nasıl kullanılacağını gösterir.  
  
## <a name="using-cdynamicaccessor"></a>CDynamicAccessor kullanma  
 [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) veritabanı şeması (veritabanının temel yapısı) olanağıyla varsa, bir veri kaynağı erişmenize olanak tanır. `CDynamicAccessor`yöntemleri sütun adları, sayı ve veri türü gibi sütun bilgileri edinin. Erişimci çalışma zamanında dinamik olarak oluşturmak için bu sütun bilgileri kullanın. Sütun bilgileri oluşturulur ve bu sınıf tarafından yönetilen bir arabellek depolanır. Arabellek kullanımından verileri elde [GetValue](../../data/oledb/cdynamicaccessor-getvalue.md) yöntemi.  
  
## <a name="example"></a>Örnek  
  
### <a name="code"></a>Kod  
  
```  
// Using_Dynamic_Accessors.cpp  
// compile with: /c /EHsc  
#include <stdio.h>  
#include <objbase.h>  
#include <atldbcli.h>  
  
int main( int argc, char* argv[] )  
{  
    HRESULT hr = CoInitialize( NULL );  
  
    CDataSource ds;  
    CSession ss;  
  
    CTable<CDynamicAccessor> rs;  
  
    // The following is an example initialization string:  
    hr = ds.OpenFromInitializationString(L"Provider=SQLOLEDB.1;"  
      L"Integrated Security=SSPI;Persist Security Info=False;"  
      L"Initial Catalog=Loginname;Data Source=your_data_source;"  
      L"Use Procedure for Prepare=1;Auto Translate=True;"  
      L"Packet Size=4096;Workstation ID=LOGINNAME01;"  
      L"Use Encryption for Data=False;"  
      L"Tag with column collation when possible=False");  
  
    hr = ss.Open( ds );  
    hr = rs.Open( ss, "Shippers" );  
  
    hr = rs.MoveFirst( );  
    while( SUCCEEDED( hr ) && hr != DB_S_ENDOFROWSET )  
    {  
        for( size_t i = 1; i <= rs.GetColumnCount( ); i++ )  
        {  
            DBTYPE type;  
            rs.GetColumnType( i, &type );  
            printf_s( "Column %d [%S] is of type %d\n",  
                      i, rs.GetColumnName( i ), type );   
  
            switch( type )  
            {  
                case DBTYPE_WSTR:  
                    printf_s( "value is %S\n",  
                              (WCHAR*)rs.GetValue( i ) );  
                break;  
                case DBTYPE_STR:  
                    printf_s( "value is %s\n",  
                              (CHAR*)rs.GetValue( i ) );  
                default:  
                    printf_s( "value is %d\n",  
                              *(long*)rs.GetValue( i ) );  
            }  
        }  
        hr = rs.MoveNext( );  
    }  
  
    rs.Close();     
    ss.Close();  
    ds.Close();  
    CoUninitialize();  
  
    return 0;  
}  
```  
  
## <a name="using-cdynamicstringaccessor"></a>CDynamicStringAccessor kullanma  
 [CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md) gibi çalışır [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md), dışındaki önemli bir şekilde. Sırada `CDynamicAccessor` sağlayıcı tarafından bildirilen yerel biçiminde veri istekleri `CDynamicStringAccessor` sağlayıcı dize veri olarak veri deposundan erişilen tüm veriler getirilemedi ister. Bu, özellikle görüntüleme ya da veri deposunun içeriği yazdırma gibi veri deposundaki değerlerin hesaplamasını gerektirmeyen basit görevler için kullanışlıdır.  
  
 Kullanım `CDynamicStringAccessor` sütun bilgileri almak için yöntemleri. Erişimci çalışma zamanında dinamik olarak oluşturmak için bu sütun bilgileri kullanın. Sütun bilgileri oluşturulur ve bu sınıf tarafından yönetilen bir arabellek depolanır. Arabellek kullanımından verileri elde [CDynamicStringAccessor::GetString](../../data/oledb/cdynamicstringaccessor-getstring.md) veya arabellek kullanmaya mağaza [CDynamicStringAccessor::SetString](../../data/oledb/cdynamicstringaccessor-setstring.md).  
  
## <a name="example"></a>Örnek  
  
### <a name="code"></a>Kod  
  
```  
// Using_Dynamic_Accessors_b.cpp  
// compile with: /c /EHsc  
#include <stdio.h>  
#include <objbase.h>  
#include <atldbcli.h>  
  
int main( int argc, char* argv[] )  
{  
    HRESULT hr = CoInitialize( NULL );  
    if (hr != S_OK)  
    {  
        exit (-1);  
    }  
  
    CDataSource ds;  
    CSession ss;  
  
    CTable<CDynamicStringAccessor> rs;  
  
    // The following is an example initialization string:  
    hr = ds.OpenFromInitializationString(L"Provider=SQLOLEDB.1;"  
      L"Integrated Security=SSPI;Persist Security Info=False;"  
      L"Initial Catalog=Loginname;Data Source=your_data_source;"  
      L"Use Procedure for Prepare=1;Auto Translate=True;"  
      L"Packet Size=4096;Workstation ID=LOGINNAME01;"  
      L"Use Encryption for Data=False;"  
      L"Tag with column collation when possible=False");  
  
    hr = ss.Open( ds );  
    hr = rs.Open( ss, "Shippers" );  
  
    hr = rs.MoveFirst( );  
    while( SUCCEEDED( hr ) && hr != DB_S_ENDOFROWSET )  
    {  
        for( size_t i = 1; i <= rs.GetColumnCount( ); i++ )  
        {  
            printf_s( "column %d value is %s\n",   
                      i, rs.GetString( i ) );  
        }  
        hr = rs.MoveNext( );  
    }  
  
    rs.Close();     
    ss.Close();  
    ds.Close();  
    CoUninitialize();  
  
   return 0;  
  
}  
```  
  
## <a name="using-cdynamicparameteraccessor"></a>CDynamicParameterAccessor Kullanma  
 [CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md) benzer [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)dışında `CDynamicParameterAccessor` çağırarak ayarlanacak parametre bilgilerini elde eder [ICommandWithParameters](https://msdn.microsoft.com/en-us/library/ms712937.aspx) arabirim. Sağlayıcı desteklemelidir `ICommandWithParameters` tüketici bu sınıfını kullanmak için.  
  
 Parametre bilgileri oluşturulur ve bu sınıf tarafından yönetilen bir arabellek depolanır. Parametre veri arabelleğinden kullanarak elde [CDynamicParameterAccessor::GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) ve [CDynamicParameterAccessor::GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md).  
  
 Örneğin, Bilgi Bankası makalesi Q058860 bakın Bu sınıf bir SQL Server saklı yordamı yürütmek ve çıkış parametre değerlerini almak için nasıl kullanılacağını gösteren "nasıl yapılır: CDynamicParameterAccessor kullanarak saklı yordamı yürütme." Bilgi Bankası makaleleri, MSDN Kitaplığı Visual Studio belgelerinde bulunur veya adresindeki [http://support.microsoft.com](http://support.microsoft.com/).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Erişimcileri kullanma](../../data/oledb/using-accessors.md)   
 [CDynamicAccessor sınıfı](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicStringAccessor sınıfı](../../data/oledb/cdynamicstringaccessor-class.md)   
 [CDynamicParameterAccessor sınıfı](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [DynamicConsumer örnek](http://msdn.microsoft.com/en-us/2ccc4c61-6749-4e83-aa81-00f8009c0dc3)