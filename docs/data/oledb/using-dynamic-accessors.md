---
description: 'Daha fazla bilgi edinin: dinamik erişimcileri kullanma'
title: Dinamik Erişimcileri Kullanma
ms.date: 10/18/2018
helpviewer_keywords:
- accessors [C++], dynamic
- dynamic accessors
ms.assetid: e5d5bfa6-2b1d-49d0-8ced-914666422431
ms.openlocfilehash: 9cc1cbf1f4c408317802698c01b228b48a5614c0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319150"
---
# <a name="using-dynamic-accessors"></a>Dinamik Erişimcileri Kullanma

Dinamik erişimciler, veritabanı şeması (temel yapı) hakkında bilginiz olmadığında bir veri kaynağına erişmenizi sağlar. OLE DB şablonları kitaplığı size yardımcı olmak için çeşitli sınıflar sağlar.

[DynamicConsumer](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer) örneği, sütun bilgilerini almak ve dinamik olarak erişimcileri oluşturmak için dinamik erişimci sınıflarının nasıl kullanılacağını gösterir.

## <a name="using-cdynamicaccessor"></a>CDynamicAccessor kullanma

[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) , veritabanı şeması (veritabanının temel yapısı) hakkında bilginiz olmadığında bir veri kaynağına erişmenizi sağlar. `CDynamicAccessor` Yöntemler sütun adları, sayı ve veri türü gibi sütun bilgileri alır. Bu sütun bilgilerini, çalışma zamanında dinamik olarak bir erişimci oluşturmak için kullanırsınız. Sütun bilgileri bu sınıf tarafından oluşturulan ve yönetilen bir arabellekte saklanır. [GetValue](./cdynamicaccessor-class.md#getvalue) yöntemini kullanarak arabellekteki verileri alın.

## <a name="example-cdynamic-accessors"></a>Örnek: CDynamic erişimcileri

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

[CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md) , tek önemli bir yol dışında [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)gibi çalışmaktadır. `CDynamicAccessor`Sağlayıcı tarafından bildirilen yerel biçimdeki verileri istediğinde, `CDynamicStringAccessor` sağlayıcının veri deposundan erişilen tüm verileri dize verileri olarak getirip getirdiğini ister. İşlem, veri deposunun içeriğini görüntüleme veya yazdırma gibi veri deposundaki değerlerin hesaplanmasını gerektirmeyen basit görevler için özellikle yararlıdır.

`CDynamicStringAccessor`Sütun bilgilerini almak için yöntemleri kullanın. Bu sütun bilgilerini, çalışma zamanında dinamik olarak bir erişimci oluşturmak için kullanırsınız. Sütun bilgileri bu sınıf tarafından oluşturulan ve yönetilen bir arabellekte saklanır. [CDynamicStringAccessor:: GetString](./cdynamicstringaccessor-class.md#getstring) kullanarak arabellekteki verileri Al veya [CDynamicStringAccessor:: SetString](./cdynamicstringaccessor-class.md#setstring)kullanarak arabelleğe depola.

## <a name="example-cdynamicstringaccessor"></a>Örnek: CDynamicStringAccessor

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

## <a name="using-cdynamicparameteraccessor"></a>CDynamicParameterAccessor kullanma

[CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md) , [](../../data/oledb/cdynamicaccessor-class.md) `CDynamicParameterAccessor` [ICommandText](/sql/relational-databases/native-client-ole-db-interfaces/icommandwithparameters) arabirimini çağırarak ayarlanacak parametre bilgilerini alan, CDynamicAccessor ile benzerdir. Sağlayıcı, `ICommandWithParameters` tüketicinin bu sınıfı kullanması için destek sağlamalıdır.

Parametre bilgileri, bu sınıf tarafından oluşturulan ve yönetilen bir arabellekte saklanır. [CDynamicParameterAccessor:: GetParam](./cdynamicparameteraccessor-class.md#getparam) ve [CDynamicParameterAccessor:: GetParamType](./cdynamicparameteraccessor-class.md#getparamtype)kullanarak arabellekteki parametre verilerini al.

Bu sınıfın bir SQL Server saklı yordamı yürütmek ve çıkış parametre değerlerini almak için nasıl kullanılacağını gösteren bir örnek için GitHub 'daki [Microsoft VCSamples](https://github.com/Microsoft/VCSamples) deposundaki [DynamicConsumer](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer) örnek koduna bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Erişimcileri kullanma](../../data/oledb/using-accessors.md)<br/>
[CDynamicAccessor sınıfı](../../data/oledb/cdynamicaccessor-class.md)<br/>
[CDynamicStringAccessor sınıfı](../../data/oledb/cdynamicstringaccessor-class.md)<br/>
[CDynamicParameterAccessor sınıfı](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
[DynamicConsumer örneği](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer)
