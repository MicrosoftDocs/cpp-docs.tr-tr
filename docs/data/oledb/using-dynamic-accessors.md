---
title: Dinamik Erişimcileri Kullanma | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2018
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
ms.openlocfilehash: 3a776043d8a65d0a037d17c1c2538a4606b4c9d1
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808387"
---
# <a name="using-dynamic-accessors"></a>Dinamik Erişimcileri Kullanma

Dinamik Erişimcileri, veritabanı şemasını (temel alınan yapısını) hiçbir bilgiye sahip olduğunda bir veri kaynağına erişmek izin verin. OLE DB şablonları kitaplığı, yardımcı olmak için çeşitli sınıflar sağlar.

[DynamicConsumer](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer) örnek sütun bilgilerini almak ve dinamik erişimciler oluşturmak için dinamik erişimci sınıflarını kullanmayı gösterir.

## <a name="using-cdynamicaccessor"></a>CDynamicAccessor kullanma

[CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) veritabanı şeması (veritabanı yapılarını) hiçbir bilgiye sahip olduğunda bir veri kaynağına erişmenizi sağlar. `CDynamicAccessor` sütun bilgisi gibi sütun adları, sayı ve veri türü yöntemleri alın. Erişimci çalışma zamanında dinamik olarak oluşturmak için bu sütun bilgileri kullanın. Sütun bilgisi oluşturulur ve bu sınıf tarafından yönetilen bir arabellek depolanır. Arabellek kullanarak veri alma [GetValue](../../data/oledb/cdynamicaccessor-getvalue.md) yöntemi.

## <a name="example"></a>Örnek

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

[CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md) gibi çalışır [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md), önemli bir şekilde hariç. Sırada `CDynamicAccessor` sağlayıcı tarafından bildirilen yerel biçiminde veri istekleri `CDynamicStringAccessor` sağlayıcı dize verileri veri deposundan erişilen tüm verileri getirme ister. İşlem, görüntüleme ya da veri deposunun içeriği yazdırma gibi veri deposundaki değerleri hesaplama gerektirmeyen basit görevler için özellikle yararlıdır.

Kullanım `CDynamicStringAccessor` sütun bilgileri almak için yöntemleri. Erişimci çalışma zamanında dinamik olarak oluşturmak için bu sütun bilgileri kullanın. Sütun bilgisi oluşturulur ve bu sınıf tarafından yönetilen bir arabellek depolanır. Arabellek kullanarak veri alma [CDynamicStringAccessor::GetString](../../data/oledb/cdynamicstringaccessor-getstring.md) veya arabelleği kullanarak mağaza [CDynamicStringAccessor::SetString](../../data/oledb/cdynamicstringaccessor-setstring.md).

## <a name="example"></a>Örnek

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

[CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md) benzer [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)dışında `CDynamicParameterAccessor` çağırarak ayarlamak için parametre bilgilerini alır [ICommandWithParameters](/sql/relational-databases/native-client-ole-db-interfaces/icommandwithparameters) arabirimi. Sağlayıcı desteklemelidir `ICommandWithParameters` tüketici Bu sınıf kullanmak için.

Parametre bilgileri oluşturulur ve bu sınıf tarafından yönetilen bir arabellek depolanır. Parametre verisi arabellekteki almak [CDynamicParameterAccessor::GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) ve [CDynamicParameterAccessor::GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md).

Bu sınıf bir SQL Server saklı yordamı yürütme ve çıkış parametresi değerleri almak için nasıl kullanılacağını gösteren bir örnek için bkz: [DynamicConsumer](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer) örnek kodda [Microsoft VCSamples](https://github.com/Microsoft/VCSamples) github deposu.

## <a name="see-also"></a>Ayrıca bkz.

[Erişimcileri Kullanma](../../data/oledb/using-accessors.md)<br/>
[CDynamicAccessor Sınıfı](../../data/oledb/cdynamicaccessor-class.md)<br/>
[CDynamicStringAccessor Sınıfı](../../data/oledb/cdynamicstringaccessor-class.md)<br/>
[CDynamicParameterAccessor Sınıfı](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
[DynamicConsumer örnek](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer)  
