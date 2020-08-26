---
title: CUtlProps Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CUtlProps
- CUtlProps::GetPropValue
- CUtlProps.GetPropValue
- GetPropValue
- CUtlProps::IsValidValue
- CUtlProps.IsValidValue
- IsValidValue
- OnPropertyChanged
- CUtlProps.OnPropertyChanged
- CUtlProps::OnPropertyChanged
- SetPropValue
- ATL::CUtlProps<T>::SetPropValue
- ATL.CUtlProps<T>.SetPropValue
- ATL.CUtlProps.SetPropValue
- CUtlProps::SetPropValue
- CUtlProps<T>::SetPropValue
- CUtlProps.SetPropValue
- CUtlProps<T>.SetPropValue
- ATL::CUtlProps::SetPropValue
helpviewer_keywords:
- CUtlProps class
- GetPropValue method
- IsValidValue method
- OnInterfaceRequested method
- OnPropertyChanged method
- SetPropValue method
ms.assetid: bb525178-765c-4e23-a110-c0fd70c05437
ms.openlocfilehash: 46fa266c5a8328bbcf7cfd1257ce1ff3e38ed2bb
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845672"
---
# <a name="cutlprops-class"></a>CUtlProps Sınıfı

Çeşitli OLE DB Özellik arabirimleri için özellikleri uygular (örneğin,, `IDBProperties` `IDBProperties` ve `IRowsetInfo` ).

## <a name="syntax"></a>Söz dizimi

```cpp
template < class T >
class ATL_NO_VTABLE CUtlProps : public CUtlPropsBase
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Öğesini içeren sınıf `BEGIN_PROPSET_MAP` .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

| Ad | Açıklama |
|-|-|
|[GetPropValue](#getpropvalue)|Özellik kümesinden bir özellik alır.|
|[IsValidValue](#isvalidvalue)|Bir özelliği ayarlamadan önce bir değeri doğrulamak için kullanılır.|
|[OnInterfaceRequested](#oninterfacerequested)|Bir tüketici nesne oluşturma arabirimindeki bir yöntemi çağırdığında isteğe bağlı bir arabirim için istekleri işler.|
|[OnPropertyChanged](#onpropertychanged)|Zincirleme özelliklerini işlemek için bir özellik ayarlandıktan sonra çağırılır.|
|[SetPropValue](#setpropvalue)|Özellik kümesindeki bir özelliği ayarlar.|

## <a name="remarks"></a>Açıklamalar

Bu sınıfın çoğu bir uygulama ayrıntısıyla yapılır.

`CUtlProps` özellikleri iç olarak ayarlamak için iki üye içerir: [GetPropValue](../../data/oledb/cutlprops-getpropvalue.md) ve [SetPropValue](../../data/oledb/cutlprops-setpropvalue.md).

Özellik kümesi eşlemesinde kullanılan makrolar hakkında daha fazla bilgi için bkz. [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md) ve [END_PROPSET_MAP](../../data/oledb/end-propset-map.md).

## <a name="cutlpropsgetpropvalue"></a><a name="getpropvalue"></a> CUtlProps:: GetPropValue

Özellik kümesinden bir özellik alır.

### <a name="syntax"></a>Söz dizimi

```cpp
OUT_OF_LINE HRESULT GetPropValue(const GUID* pguidPropSet,
   DBPROPID dwPropId,
   VARIANT* pvValue);
```

#### <a name="parameters"></a>Parametreler

*pguidPropSet*<br/>
'ndaki PropSet için GUID.

*Dwpropıd*<br/>
'ndaki Özellik dizini.

*pvValue*<br/>
dışı Yeni özellik değerini içeren bir varyant işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

`Failure` hata durumunda ve başarılı olursa S_OK.

## <a name="cutlpropsisvalidvalue"></a><a name="isvalidvalue"></a> CUtlProps:: IsValidValue

Bir özelliği ayarlamadan önce bir değeri doğrulamak için kullanılır.

### <a name="syntax"></a>Söz dizimi

```cpp
virtual HRESULT CUtlPropsBase::IsValidValue(ULONG /* iCurSet */,
   DBPROP* pDBProp);
```

#### <a name="parameters"></a>Parametreler

*ıcurset*<br/>
Özellik kümesi dizisine Dizin; yalnızca bir özellik kümesi varsa sıfırdır.

*pDBProp*<br/>
Özellik KIMLIĞI ve bir [DBPROP](/previous-versions/windows/desktop/ms717970(v=vs.85)) yapısındaki yeni değer.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT. Varsayılan dönüş değeri S_OK.

### <a name="remarks"></a>Açıklamalar

Bir özelliği ayarlamak için kullanmak üzere olduğunuz bir değer üzerinde çalıştırmak istediğiniz doğrulama yordamlarınızın varsa, bu işlevi geçersiz kılmanız gerekir. Örneğin, geçerli bir değeri belirleyebilmek için parola tablosuna karşı DBPROP_AUTH_PASSWORD doğrulayabilirsiniz.

## <a name="cutlpropsoninterfacerequested"></a><a name="oninterfacerequested"></a> CUtlProps:: Onınterfacerequyilmiş

Bir tüketici nesne oluşturma arabirimlerinden birindeki bir yöntemi çağırdığında isteğe bağlı bir arabirim için istekleri işler.

### <a name="syntax"></a>Söz dizimi

```cpp
virtual HRESULT CUtlPropsBase::OnInterfaceRequested(REFIID riid);
```

#### <a name="parameters"></a>Parametreler

*riıd*<br/>
'ndaki İstenen arabirim için IID. Daha fazla ayrıntı için, *riid* `ICommand::Execute` *OLE DB PROGRAMCı başvurusu* ( *MDAC SDK*'da) içindeki riid parametresinin açıklamasına bakın.

### <a name="remarks"></a>Açıklamalar

`OnInterfaceRequested` bir tüketici, nesne oluşturma arabirimlerinden (,, veya gibi) birindeki bir yöntemi çağırdığında isteğe bağlı arabirim için tüketici isteklerini işler `IDBCreateSession` `IDBCreateCommand` `IOpenRowset` `ICommand` . İstenen arabirim için karşılık gelen OLE DB özelliğini ayarlar. Örneğin, tüketici istediğinde `IID_IRowsetLocate` `OnInterfaceRequested` `DBPROP_IRowsetLocate` arabirimini ayarlar. Bunun yapılması, satır kümesi oluşturma sırasında doğru durumu korur.

Bu yöntem, tüketici veya çağırdığında çağrılır `IOpenRowset::OpenRowset` `ICommand::Execute` .

Bir tüketici bir nesne açarsa ve isteğe bağlı bir arabirim isterse, sağlayıcı bu arabirimle ilişkili özelliği VARIANT_TRUE olarak ayarlamış olmalıdır. Özelliğe özgü işleme izin vermek için, `OnInterfaceRequested` sağlayıcının `Execute` yöntemi çağrılmadan önce çağrılır. Varsayılan olarak, `OnInterfaceRequested` aşağıdaki arayüzleri işler:

- `IRowsetLocate`

- `IRowsetChange`

- `IRowsetUpdate`

- `IConnectionPointContainer`

- `IRowsetScroll`

Diğer arabirimleri işlemek istiyorsanız, işlevleri işlemek için veri kaynağınız, oturum, komut veya satır kümesi sınıfınıza bu işlevi geçersiz kılın. Geçersiz kılma özelliği, ayar özelliklerinin aynı zamanda zincirleme özellikleri de ayarlayadiğinden emin olmak için normal set/Get özellikleri arabirimlerini almalıdır (bkz. [OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md)).

## <a name="cutlpropsonpropertychanged"></a><a name="onpropertychanged"></a> CUtlProps:: OnPropertyChanged

Zincirleme özelliklerini işlemek için bir özellik ayarlandıktan sonra çağırılır.

### <a name="syntax"></a>Söz dizimi

```cpp
virtual HRESULT OnPropertyChanged(ULONG /* iCurSet */,
   DBPROP* pDBProp);
```

#### <a name="parameters"></a>Parametreler

*ıcurset*<br/>
Özellik kümesi dizisine Dizin; yalnızca bir özellik kümesi varsa sıfırdır.

*pDBProp*<br/>
Özellik KIMLIĞI ve bir [DBPROP](/previous-versions/windows/desktop/ms717970(v=vs.85)) yapısındaki yeni değer.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT. Varsayılan dönüş değeri S_OK.

### <a name="remarks"></a>Açıklamalar

Yer işaretleri veya değerleri başka bir özelliğin değerine bağımlı olan güncelleştirmeler gibi zincirleme özelliklerini işlemek istiyorsanız, bu işlevi geçersiz kılmanız gerekir.

### <a name="example"></a>Örnek

Bu işlevde Kullanıcı, parametresindeki Özellik KIMLIĞINI alır `DBPROP*` . Şimdi, KIMLIĞI bir özellikle zincirle karşılaştırmak mümkündür. Özelliği bulunduğunda, `SetProperties` artık diğer özellikle birlikte ayarlanacak özelliği ile çağırılır. Bu durumda, bir `DBPROP_IRowsetLocate` , veya özelliğini alırsa, `DBPROP_LITERALBOOKMARKS` `DBPROP_ORDEREDBOOKMARKS` bir tane `DBPROP_BOOKMARKS` özelliği ayarlayabilir.

[!code-cpp[NVC_OLEDB_Provider#2](../../data/oledb/codesnippet/cpp/cutlprops-onpropertychanged_1.h)]

## <a name="cutlpropssetpropvalue"></a><a name="setpropvalue"></a> CUtlProps:: SetPropValue

Özellik kümesindeki bir özelliği ayarlar.

### <a name="syntax"></a>Söz dizimi

```cpp
HRESULT SetPropValue(const GUID* pguidPropSet,
   DBPROPID dwPropId,
   VARIANT* pvValue);
```

#### <a name="parameters"></a>Parametreler

*pguidPropSet*<br/>
'ndaki PropSet için GUID.

*Dwpropıd*<br/>
'ndaki Özellik dizini.

*pvValue*<br/>
'ndaki Yeni özellik değerini içeren bir varyant işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

`Failure` hata durumunda ve başarılı olursa S_OK.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB sağlayıcı şablonu mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)
