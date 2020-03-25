---
title: Tüketici Sihirbazı Tarafından Oluşturulan Yöntemler
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB consumers, wizard-generated classes and methods
ms.assetid: d80ee51c-8bb3-4dca-8760-5808e0fb47b4
ms.openlocfilehash: ce2442909fd318187a1508300a75ff4f634b3410
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211516"
---
# <a name="consumer-wizard-generated-methods"></a>Tüketici Sihirbazı Tarafından Oluşturulan Yöntemler

::: moniker range="vs-2019"

ATL OLE DB Tüketici Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz. İşlevselliği el ile de ekleyebilirsiniz.

::: moniker-end

::: moniker range="<=vs-2017"

**ATL OLE DB Tüketici Sihirbazı** ve **MFC Uygulama Sihirbazı** , bilmeniz gereken belirli işlevleri oluşturur. Bazı yöntemler öznitelikli projelerde farklı şekilde uygulandığından bazı uyarılar vardır; Her bir durum aşağıda ele alınmıştır. Eklenen kodu görüntüleme hakkında daha fazla bilgi için bkz. [eklenen kodda hata ayıklama](/visualstudio/debugger/how-to-debug-injected-code).

- `OpenAll` veri kaynağını, satır kümelerini açar ve kullanılabilir olmaları durumunda yer imlerini etkinleştirir.

- `CloseAll` tüm açık satır kümelerini kapatır ve tüm komut yürütmelerini yayınlar.

- `OpenRowset` tüketicinin satır kümesini veya satır kümelerini açmak için `OpenAll` tarafından çağrılır.

- `GetRowsetProperties`, satır kümesinin özellik kümesine, özelliklerin ayarlanbileceği bir işaretçi alır.

- `OpenDataSource` veri **bağlantısı özellikleri** iletişim kutusunda belirttiğiniz başlatma dizesini kullanarak veri kaynağını açar.

- `CloseDataSource` veri kaynağını uygun bir şekilde kapatır.

## <a name="openall-and-closeall"></a>OpenAll ve CloseAll

```cpp
HRESULT OpenAll();

void CloseAll();
```

Aşağıdaki örnek, aynı komutu tekrar tekrar çalıştırdığınızda `OpenAll` ve `CloseAll` nasıl çağrılacağını gösterir. `CloseAll`yerine `Close` ve `ReleaseCommand` çağıran bir çeşitleme gösteren [CCommand:: Close](../../data/oledb/ccommand-close.md)içindeki kod örneğini karşılaştırın.

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

Bir `HasBookmark` yöntemi tanımlarsanız, `OpenAll` kodu `DBPROP_IRowsetLocate` özelliğini ayarlar; Bunu yalnızca sağlayıcınız bu özelliği destekliyorsa yaptığınızdan emin olun.

## <a name="openrowset"></a>OpenRowset

```cpp
// OLE DB Template version:
HRESULT OpenRowset(DBPROPSET* pPropSet = NULL)
// Attribute-injected version:
HRESULT OpenRowset(const CSession& session, LPCWSTR szCommand = NULL);
```

`OpenAll` tüketicideki satır kümesini veya satır kümelerini açmak için bu yöntemi çağırır. Genellikle, birden fazla veri kaynağı/oturumu/satır kümesi ile çalışmak istemediğiniz müddetçe `OpenRowset` çağırmanız gerekmez. `OpenRowset`, komut veya tablo sınıfı üstbilgi dosyasında bildirilmiştir:

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

Öznitelikleri bu yöntemi farklı şekilde uygular. Bu sürüm, farklı bir tane geçirebilseniz de bir oturum nesnesi ve db_command belirtilen komut dizesine varsayılan olarak bir komut dizesi alır. Bir `HasBookmark` yöntemi tanımlarsanız, `OpenRowset` kodu `DBPROP_IRowsetLocate` özelliğini ayarlar; Bunu yalnızca sağlayıcınız bu özelliği destekliyorsa yaptığınızdan emin olun.

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

Bu yöntem, satır kümesinin özellik kümesine bir işaretçi alır; Bu işaretçiyi, `DBPROP_IRowsetChange`gibi özellikleri ayarlamak için kullanabilirsiniz. `GetRowsetProperties`, Kullanıcı kayıt sınıfında aşağıdaki gibi kullanılır. Ek satır kümesi özelliklerini ayarlamak için bu kodu değiştirebilirsiniz:

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

Sihirbaz tarafından tanımlanan bir ile çakışabileceğinden, genel bir `GetRowsetProperties` yöntemi tanımlamanız gerekmez. Bu, şablonlu ve öznitelikli projelerle aldığınız, sihirbaz tarafından oluşturulan bir yöntemdir; öznitelikler bu kodu ekleme.

## <a name="opendatasource-and-closedatasource"></a>OpenDataSource ve CloseDataSource

```cpp
HRESULT OpenDataSource();

void CloseDataSource();
```

### <a name="remarks"></a>Açıklamalar

Sihirbaz `OpenDataSource` ve `CloseDataSource`yöntemlerini tanımlar; `OpenDataSource` [CDataSource:: Openfrominializationstring](../../data/oledb/cdatasource-openfrominitializationstring.md)öğesini çağırır.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[Sihirbaz Kullanarak bir OLE DB Tüketicisi Oluşturma](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)
