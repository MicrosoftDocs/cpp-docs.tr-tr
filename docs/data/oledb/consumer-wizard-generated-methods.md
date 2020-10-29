---
title: Tüketici Sihirbazı Tarafından Oluşturulan Yöntemler
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB consumers, wizard-generated classes and methods
ms.assetid: d80ee51c-8bb3-4dca-8760-5808e0fb47b4
ms.openlocfilehash: 15d41aabee174a409ad11e4422292bcea5f10bbf
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919130"
---
# <a name="consumer-wizard-generated-methods"></a>Tüketici Sihirbazı Tarafından Oluşturulan Yöntemler

::: moniker range="msvc-160"

ATL OLE DB Tüketici Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz. İşlevselliği el ile de ekleyebilirsiniz.

::: moniker-end

::: moniker range="<=msvc-150"

**ATL OLE DB Tüketici Sihirbazı** ve **MFC Uygulama Sihirbazı** , bilmeniz gereken belirli işlevleri oluşturur. Bazı yöntemler öznitelikli projelerde farklı şekilde uygulandığından bazı uyarılar vardır; Her bir durum aşağıda ele alınmıştır. Eklenen kodu görüntüleme hakkında daha fazla bilgi için bkz. [eklenen kodda hata ayıklama](/visualstudio/debugger/how-to-debug-injected-code).

- `OpenAll` veri kaynağını, satır kümelerini açar ve kullanılabilir olmaları durumunda yer imlerini etkinleştirir.

- `CloseAll` Tüm açık satır kümelerini kapatır ve tüm komut yürütmelerini yayınlar.

- `OpenRowset` , `OpenAll` tüketicinin satır kümesini veya satır kümelerini açmak için tarafından çağırılır.

- `GetRowsetProperties` satır kümesinin özellik kümesine, özelliklerin ayarlanbileceği bir işaretçi alır.

- `OpenDataSource` veri **bağlantısı özellikleri** iletişim kutusunda belirttiğiniz başlatma dizesini kullanarak veri kaynağını açar.

- `CloseDataSource` veri kaynağını uygun bir şekilde kapatır.

## <a name="openall-and-closeall"></a>OpenAll ve CloseAll

```cpp
HRESULT OpenAll();

void CloseAll();
```

Aşağıdaki örnek, `OpenAll` `CloseAll` aynı komutu tekrar tekrar çalıştırdığınızda nasıl çağrılacağını gösterir. Ve yerine çağıran bir varyasyon gösteren [CCommand:: Close](./ccommand-class.md#close)içindeki kod örneğini karşılaştırın `Close` `ReleaseCommand` `CloseAll` .

```cpp
int main(int argc, char* argv[])
{
   HRESULT hr;

   hr = CoInitialize(NULL);

   CCustOrdersDetail rs;      // Your CCommand-derived class
   rs.m_OrderID = 10248;      // Open order 10248
   hr = rs.OpenAll();         // (Open also executes the command)
   hr = rs.MoveFirst();         // Move to the first row and print it
   printf( "Name: %s, Unit Price: %d, Quantity: %d, Discount %d, Extended Price %d\n", rs.m_ProductName, rs.m_UnitPrice.int64, rs.m_Quantity, rs.m_Discount, rs.m_ExtendedPrice.int64 );

   // Close the first command execution
   rs.Close();

   rs.m_OrderID = 10249;      // Open order 10249 (a new order)
   hr = rs.Open();            // (Open also executes the command)
   hr = rs.MoveFirst();         // Move to the first row and print it
   printf( "Name: %s, Unit Price: %d, Quantity: %d, Discount %d, Extended Price %d\n", rs.m_ProductName, rs.m_UnitPrice.int64, rs.m_Quantity, rs.m_Discount, rs.m_ExtendedPrice.int64 );

   // Close the second command execution;
   // Instead of rs.CloseAll() you could call
   // rs.Close() and rs.ReleaseCommand():
   rs.CloseAll();

   CoUninitialize();
   return 0;
}
```

### <a name="remarks"></a>Açıklamalar

Bir `HasBookmark` Yöntem tanımlarsanız, `OpenAll` kod `DBPROP_IRowsetLocate` özelliği ayarlar; bunu yalnızca sağlayıcınız bu özelliği destekliyorsa yaptığınızdan emin olun.

## <a name="openrowset"></a>OpenRowset

```cpp
// OLE DB Template version:
HRESULT OpenRowset(DBPROPSET* pPropSet = NULL)
// Attribute-injected version:
HRESULT OpenRowset(const CSession& session, LPCWSTR szCommand = NULL);
```

`OpenAll` tüketicideki satır kümesini veya satır kümelerini açmak için bu yöntemi çağırır. Genellikle, `OpenRowset` birden fazla veri kaynağı/oturumu/satır kümesi ile çalışmak istemediğiniz müddetçe çağırmanız gerekmez. `OpenRowset` komut veya tablo sınıfı üstbilgi dosyasında bildirildiği:

```cpp
// OLE DB Template version:
HRESULT OpenRowset(DBPROPSET *pPropSet = NULL)
{
   HRESULT hr = Open(m_session, NULL, pPropSet);
   #ifdef _DEBUG
   if(FAILED(hr))
      AtlTraceErrorRecords(hr);
   #endif
   return hr;
}
```

Öznitelikleri bu yöntemi farklı şekilde uygular. Bu sürüm, farklı bir tane geçirebilseniz de bir oturum nesnesi ve db_command belirtilen komut dizesine varsayılan olarak bir komut dizesi alır. Bir `HasBookmark` Yöntem tanımlarsanız, `OpenRowset` kod `DBPROP_IRowsetLocate` özelliği ayarlar; bunu yalnızca sağlayıcınız bu özelliği destekliyorsa yaptığınızdan emin olun.

```cpp
// Attribute-injected version:
HRESULT OpenRowset(const CSession& session, LPCWSTR szCommand=NULL)
{

   DBPROPSET *pPropSet = NULL;
   CDBPropSet propset(DBPROPSET_ROWSET);
   __if_exists(HasBookmark)

   {
      propset.AddProperty(DBPROP_IRowsetLocate, true);
      pPropSet= &propset;
      }
...
}
```

## <a name="getrowsetproperties"></a>GetRowsetProperties

```cpp
void GetRowsetProperties(CDBPropSet* pPropSet);
```

Bu yöntem, satır kümesinin özellik kümesine bir işaretçi alır; Bu işaretçiyi, gibi özellikleri ayarlamak için kullanabilirsiniz `DBPROP_IRowsetChange` . `GetRowsetProperties` , Kullanıcı kayıt sınıfında aşağıdaki gibi kullanılır. Ek satır kümesi özelliklerini ayarlamak için bu kodu değiştirebilirsiniz:

```cpp
void GetRowsetProperties(CDBPropSet* pPropSet)
{
   pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
   pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
   pPropSet->AddProperty(DBPROP_IRowsetChange, true, DBPROPOPTIONS_OPTIONAL);
   pPropSet->AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE);
}
```

### <a name="remarks"></a>Açıklamalar

`GetRowsetProperties`Sihirbaz tarafından tanımlanan bir ile çakışabileceğinden, genel bir yöntem tanımlamamalısınız. Bu, şablonlu ve öznitelikli projelerle aldığınız, sihirbaz tarafından oluşturulan bir yöntemdir; öznitelikler bu kodu ekleme.

## <a name="opendatasource-and-closedatasource"></a>OpenDataSource ve CloseDataSource

```cpp
HRESULT OpenDataSource();

void CloseDataSource();
```

### <a name="remarks"></a>Açıklamalar

Sihirbaz yöntemleri tanımlar `OpenDataSource` ve `CloseDataSource` ; `OpenDataSource` [CDataSource:: OpenFromInitializationString](./cdatasource-class.md#openfrominitializationstring)öğesini çağırır.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[Sihirbaz kullanarak OLE DB tüketicisi oluşturma](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)
