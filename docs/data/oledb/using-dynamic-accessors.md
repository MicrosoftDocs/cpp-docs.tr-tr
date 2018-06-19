---
title: Dinamik Erişimcileri Kullanma | Microsoft Docs
ms.custom: ''
ms.date: 02/14/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- accessors [C++], dynamic
- dynamic accessors
ms.assetid: e5d5bfa6-2b1d-49d0-8ced-914666422431
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 700a959742fafd4478659ff08821b043aff8bc14
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33111978"
---
# <a name="using-dynamic-accessors"></a>Dinamik Erişimcileri Kullanma

Dinamik erişimciler veritabanı şeması (temel yapısı) olanağıyla varsa, bir veri kaynağına erişmek sağlar. OLE DB şablonları kitaplığı, bu yapmanıza yardımcı olmak için çeşitli sınıflar sağlar.

[DynamicConsumer](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer) örnek dinamik erişimciyi sınıfları sütun bilgi edinebilir ve dinamik olarak erişimciler oluşturmak için nasıl kullanılacağını gösterir.

## <a name="using-cdynamicaccessor"></a>CDynamicAccessor kullanma

[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) veritabanı şeması (veritabanının temel yapısı) olanağıyla varsa, bir veri kaynağı erişmenize olanak tanır. `CDynamicAccessor` yöntemleri sütun adları, sayı ve veri türü gibi sütun bilgileri edinin. Erişimci çalışma zamanında dinamik olarak oluşturmak için bu sütun bilgileri kullanın. Sütun bilgileri oluşturulur ve bu sınıf tarafından yönetilen bir arabellek depolanır. Arabellek kullanımından verileri elde [GetValue](../../data/oledb/cdynamicaccessor-getvalue.md) yöntemi.

## <a name="example"></a>Örnek

### <a name="code"></a>Kod

```cpp
// Using_Dynamic_Accessors.cpp
// compile with: /c /EHsc
#include <stdio.h>
#include <objbase.h>
#include <atldbcli.h>

int main(int argc, char* argv[] )
{
    HRESULT hr = CoInitialize(NULL );

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

    hr = ss.Open(ds );
    hr = rs.Open(ss, "Shippers" );

    hr = rs.MoveFirst();
    while(SUCCEEDED(hr ) && hr != DB_S_ENDOFROWSET )
    {
        for(size_t i = 1; i <= rs.GetColumnCount(); i++ )
        {
            DBTYPE type;
            rs.GetColumnType(i, &type );
            printf_s( "Column %d [%S] is of type %d\n",
                      i, rs.GetColumnName(i ), type );

            switch(type )
            {
                case DBTYPE_WSTR:
                    printf_s( "value is %S\n",
                              (WCHAR*)rs.GetValue(i ) );
                break;
                case DBTYPE_STR:
                    printf_s( "value is %s\n",
                              (CHAR*)rs.GetValue(i ) );
                default:
                    printf_s( "value is %d\n",
                              *(long*)rs.GetValue(i ) );
            }
        }
        hr = rs.MoveNext();
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

```cpp
// Using_Dynamic_Accessors_b.cpp
// compile with: /c /EHsc
#include <stdio.h>
#include <objbase.h>
#include <atldbcli.h>

int main(int argc, char* argv[] )
{
    HRESULT hr = CoInitialize(NULL );
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

    hr = ss.Open(ds );
    hr = rs.Open(ss, "Shippers" );

    hr = rs.MoveFirst();
    while(SUCCEEDED(hr ) && hr != DB_S_ENDOFROWSET )
    {
        for(size_t i = 1; i <= rs.GetColumnCount(); i++ )
        {
            printf_s( "column %d value is %s\n",
                      i, rs.GetString(i ) );
        }
        hr = rs.MoveNext();
    }

    rs.Close();
    ss.Close();
    ds.Close();
    CoUninitialize();

   return 0;
}
```

## <a name="using-cdynamicparameteraccessor"></a>CDynamicParameterAccessor Kullanma

[CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md) benzer [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)dışında `CDynamicParameterAccessor` çağırarak ayarlanacak parametre bilgilerini elde eder [ICommandWithParameters](/sql/relational-databases/native-client-ole-db-interfaces/icommandwithparameters) arabirim. Sağlayıcı desteklemelidir `ICommandWithParameters` tüketici bu sınıfını kullanmak için.

Parametre bilgileri oluşturulur ve bu sınıf tarafından yönetilen bir arabellek depolanır. Parametre veri arabelleğinden kullanarak elde [CDynamicParameterAccessor::GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) ve [CDynamicParameterAccessor::GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md).

Bu sınıf bir SQL Server saklı yordamı yürütmek ve çıkış parametresi değerlerini almak için nasıl kullanılacağını gösteren bir örnek için bkz: [DynamicConsumer](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer) örnek kodda [Microsoft VCSamples](https://github.com/Microsoft/VCSamples) GitHub deposunu.

## <a name="see-also"></a>Ayrıca bkz.

[Erişimcileri Kullanma](../../data/oledb/using-accessors.md)  
[CDynamicAccessor Sınıfı](../../data/oledb/cdynamicaccessor-class.md)  
[CDynamicStringAccessor Sınıfı](../../data/oledb/cdynamicstringaccessor-class.md)  
[CDynamicParameterAccessor Sınıfı](../../data/oledb/cdynamicparameteraccessor-class.md)  
[DynamicConsumer örnek](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer)  
