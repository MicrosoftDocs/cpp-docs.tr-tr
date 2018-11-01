---
title: CRowsetImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CRowsetImpl
- ATL.CRowsetImpl
- ATL::CRowsetImpl
- CRowsetImpl.NameFromDBID
- CRowsetImpl::NameFromDBID
- CRowsetImpl.SetCommandText
- CRowsetImpl::SetCommandText
- GetColumnInfo
- CRowsetImpl.GetColumnInfo
- CRowsetImpl::GetColumnInfo
- CRowsetImpl::GetCommandFromID
- GetCommandFromID
- CRowsetImpl.GetCommandFromID
- CRowsetImpl.ValidateCommandID
- CRowsetImpl::ValidateCommandID
- CRowsetImpl.m_rgRowData
- CRowsetImpl::m_rgRowData
- CRowsetImpl::m_strCommandText
- CRowsetImpl.m_strCommandText
- CRowsetImpl::m_strIndexText
- CRowsetImpl.m_strIndexText
helpviewer_keywords:
- CRowsetImpl class
- NameFromDBID method
- SetCommandText method
- GetColumnInfo method
- GetCommandFromID method
- ValidateCommandID method
- m_rgRowData
- m_strCommandText
- m_strIndexText
ms.assetid: e97614b3-b11d-4806-a0d3-b9401331473f
ms.openlocfilehash: e62e58273daf74d8551efb2165fe71d6fb7d3181
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50429992"
---
# <a name="crowsetimpl-class"></a>CRowsetImpl Sınıfı

Standart bir OLE DB satır kümesi uygulaması, birçok uygulama arabirimlerin birden çok devralma gerek kalmadan sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
   class T,
   class Storage,
   class CreatorClass,
   class ArrayType = CAtlArray<Storage>, 
   class RowClass = CSimpleRow, 
   class RowsetInterface = IRowsetImpl <T, IRowset> 
>
class CRowsetImpl :  
   public CComObjectRootEx<CreatorClass::_ThreadModel>, 
   public CRowsetBaseImpl<T, Storage, ArrayType, RowsetInterface>, 
   public IRowsetInfoImpl<T, CreatorClass::_PropClass>
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Öğesinden türetilen kullanıcı sınıfı `CRowsetImpl`.

*Depolama*<br/>
Kullanıcı kayıt sınıfı.

*CreatorClass*<br/>
Satır kümesi özelliklerini içeren sınıf; genellikle komutu.

*ArrayType*<br/>
Satır kümesinin veriler için depolama olarak davranacak bir sınıf. Bu parametre için varsayılan olarak `CAtlArray`, ancak gerekli işlevselliği destekleyen herhangi bir sınıf olabilir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldb.h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[NameFromDBID](#namefromdbid)|Bir dizeden ayıklar bir `DBID` ve kendisine kopyalar *bstr* geçirildi.|
|[SetCommandText](#setcommandtext)|Doğrular ve depolar `DBID`iki dizeyi s ([m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) ve [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)).|

### <a name="overridable-methods"></a>Geçersiz kılınabilir yöntemleri

|||
|-|-|
|[GetColumnInfo](#getcolumninfo)|Belirli istemci isteği için sütun bilgileri alır.|
|[GetCommandFromID](#getcommandfromid)|Her ikisi de parametreleri dize değerleri içeriyorsa ve bu durumda olup olmadığını kontrol eder, veri üyelerine dize değerleri kopyalar [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) ve [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).|
|[ValidateCommandID](#validatecommandid)|Ya da bakın veya her ikisini de denetler `DBID`s dize değerleri içeren ve bu durumda, veri üyeleri için kopyalar [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) ve [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).|

### <a name="data-members"></a>Veri üyeleri

|||
|-|-|
|[m_rgRowData](#rgrowdata)|Varsayılan olarak, bir `CAtlArray` için kullanıcı kayıt şablon bağımsız değişkeni üzerinde templatizes `CRowsetImpl`. Başka bir dizi türü sınıf değiştirerek kullanılabilir `ArrayType` şablon bağımsız değişkeni `CRowsetImpl`.|
|[m_strCommandText](#strcommandtext)|Satır kümesinin başlangıç komutu içerir.|
|[m_strIndexText](#strindextext)|Satır kümesinin başlangıç dizini içeriyor.|

## <a name="remarks"></a>Açıklamalar

`CRowsetImpl` geçersiz kılmalar statik upcasts biçiminde sağlar. Yöntemleri, belirli bir satır kümesi komut metni doğrulayacak şekilde denetler. Kendi oluşturabilirsiniz `CRowsetImpl`-sınıfı birden fazla devralınan uygulama arabirimlerinizi yaparak stil. Kendisi için sağlamalısınız uygulamasıdır tek yöntem `Execute`. Ne tür bir satır kümesi oluşturmakta olduğunuz bağlı olarak, oluşturucu yöntemleri için farklı imzalara beklediği `Execute`. Örneğin kullanıyorsanız, bir `CRowsetImpl`-türetilmiş sınıf şeması satır kümesi uygulamak için `Execute` yöntemi aşağıdaki imzası olacaktır:

`HRESULT Execute(LONG* pcRows, ULONG cRestrictions, const VARIANT* rgRestrictions)`

Oluşturuyorsanız bir `CRowsetImpl`-türetilmiş sınıf, bir komut veya oturumunun satır uygulamak için `Execute` yöntemi aşağıdaki imzası olacaktır:

`HRESULT Execute(LONG* pcRows, DBPARAMS* pParams)`

Herhangi bir uygulama `CRowsetImpl`-türetilmiş `Execute` yöntemleri, iç veri arabelleklerinin doldurmanız gerekir ([m_rgRowData](../../data/oledb/crowsetimpl-m-rgrowdata.md)).

## <a name="namefromdbid"></a> CRowsetImpl::namefromdbıd

Bir dizeden ayıklar bir `DBID` ve kendisine kopyalar *bstr* geçirildi.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT CRowsetBaseImpl::NameFromDBID(DBID* pDBID,
   CComBSTR& bstr,
   bool bIndex);
```

#### <a name="parameters"></a>Parametreler

*pDBID*<br/>
[in] Bir işaretçi `DBID` ayıklanacağı bir dize.

*BSTR*<br/>
[in] A [CComBSTR](../../atl/reference/ccombstr-class.md) bir kopyasını yerleştirmek için başvuru `DBID` dize.

*bIndex*<br/>
[in] **true** dizin varsa `DBID`; **false** bir tablo `DBID`.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT. Bağlı olarak `DBID` bir tablo veya dizin (çağrılarınızla *bIndex*), yöntem ya da DB_E_NOINDEX veya DB_E_NOTABLE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi çağıran `CRowsetImpl` uygulamaları [ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md) ve [Getcommandfromıd](../../data/oledb/crowsetimpl-getcommandfromid.md).

## <a name="setcommandtext"></a> CRowsetImpl::setCommandText

Doğrular ve depolar `DBID`iki dizeyi s ([m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) ve [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)).

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT CRowsetBaseImpl::SetCommandText(DBID* pTableID,
   DBID* pIndexID);
```

#### <a name="parameters"></a>Parametreler

*pTableID*<br/>
[in] Bir işaretçi `DBID` temsil eden tablo kimliği.

*pIndexID*<br/>
[in] Bir işaretçi `DBID` dizin kimliği temsil eden

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

### <a name="remarks"></a>Açıklamalar

`SetCommentText` Yöntemi tarafından çağrılır `CreateRowset`, statik bir yöntemi şablonlaştırılmış `IOpenRowsetImpl`.

Bu yöntemi çağırarak işini Temsilciler [ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md) ve [Getcommandfromıd](../../data/oledb/crowsetimpl-getcommandfromid.md) upcasted bir işaretçi aracılığıyla.

## <a name="getcolumninfo"></a> CRowsetImpl::GetColumnInfo

Belirli istemci isteği için sütun bilgileri alır.

### <a name="syntax"></a>Sözdizimi

```cpp
static ATLCOLUMNINFO* CRowsetBaseImpl::GetColumnInfo(T* pv,
   ULONG* pcCols);
```

#### <a name="parameters"></a>Parametreler

*BD*<br/>
[in] Kullanıcının bir işaretçiye `CRowsetImpl` türetilmiş sınıf.

*pcCols*<br/>
[in] (Bir sayıya çıkış) bir işaretçi sütun döndürdü.

### <a name="return-value"></a>Dönüş Değeri

Statik bir işaretçiye `ATLCOLUMNINFO` yapısı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Gelişmiş bir geçersiz kılma kullanılır.

Bu yöntem, belirli bir istemci isteği için sütun bilgileri almak için birkaç temel uygulama sınıfları tarafından çağrılır. Genellikle, bu yöntem çağrılır `IColumnsInfoImpl`. Bu yöntemi geçersiz kılarsanız, yöntem bir sürümünü yerleştirmeniz gerekir, `CRowsetImpl`-türetilmiş sınıf. Yöntem şablonlaştırılmış olmayan bir sınıfta yerleştirilmiş olabilir çünkü değiştirmeli *pv* uygun `CRowsetImpl`-türetilmiş sınıf.

Aşağıdaki örnek, gösterir `GetColumnInfo` kullanım. Bu örnekte, `CMyRowset` olduğu bir `CRowsetImpl`-türetilmiş sınıf. Geçersiz kılmak için `GetColumnInfo` bu sınıfın tüm örnekleri için aşağıdaki yöntemi yerleştirin `CMyRowset` sınıf tanımını:

[!code-cpp[NVC_OLEDB_Provider#1](../../data/oledb/codesnippet/cpp/crowsetimpl-getcolumninfo_1.h)]

## <a name="getcommandfromid"></a> CRowsetImpl::getcommandfromıd

Her ikisi de parametreleri dize değerleri içeriyorsa ve bu durumda olup olmadığını kontrol eder, veri üyelerine dize değerleri kopyalar [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) ve [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT CRowsetBaseImpl::GetCommandFromID(DBID* pTableID,
   DBID* pIndexID);
```

#### <a name="parameters"></a>Parametreler

*pTableID*<br/>
[in] Bir işaretçi `DBID` tablo kimliği temsil eden

*pIndexID*<br/>
[in] Bir işaretçi `DBID` dizin kimliği temsil eden

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Bu yöntem bir statik yukarı çevrim tarafından aracılığıyla çağrılır `CRowsetImpl` veri üyeleri doldurmak için [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) ve [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md). Varsayılan olarak, bu yöntem, her ikisi de parametreleri dize değerleri içerip içermediğini görmek için denetler. Bunlar dize değer içermiyorsa, bu yöntem veri üyelerine dize değerleri kopyalar. Bu imzaya sahip bir yöntemi yerleştirerek, `CRowsetImpl`-türetilmiş sınıf, taban uygulamasını yerine yönteminiz olarak adlandırılır.

## <a name="validatecommandid"></a> CRowsetImpl::ValidateCommandID

Ya da bakın veya her ikisini de denetler `DBID`s dize değerleri içeren ve bu durumda, veri üyeleri için kopyalar [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) ve [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT CRowsetBaseImpl::ValidateCommandID(DBID* pTableID,
   DBID* pIndexID);
```

#### <a name="parameters"></a>Parametreler

*pTableID*<br/>
[in] Bir işaretçi `DBID` temsil eden tablo kimliği.

*pIndexID*<br/>
[in] Bir işaretçi `DBID` dizin kimliği temsil eden

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Bu yöntem bir statik yukarı çevrim tarafından aracılığıyla çağrılır `CRowsetImpl` veri üyelerini doldurmak için [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) ve [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md). Varsayılan olarak, bu yöntem, ya da bakın veya her ikisini de denetler. `DBID`s dize değerleri içeren ve bu durumda, veri üyeleri için kopyalar. Bu imzaya sahip bir yöntemi yerleştirerek, `CRowsetImpl`-türetilmiş sınıf, taban uygulamasını yerine yönteminiz olarak adlandırılır.

## <a name="rgrowdata"></a> CRowsetImpl::m_rgRowData

Varsayılan olarak, bir `CAtlArray` için kullanıcı kayıt şablon bağımsız değişkeni üzerinde templatizes `CRowsetImpl`.

### <a name="syntax"></a>Sözdizimi

```cpp
ArrayType CRowsetBaseImpl::m_rgRowData;
```

### <a name="remarks"></a>Açıklamalar

*ArrayType* şablon parametresi `CRowsetImpl`.

## <a name="strcommandtext"></a> CRowsetImpl::m_strCommandText

Satır kümesinin başlangıç komutu içerir.

### <a name="syntax"></a>Sözdizimi

```cpp
CComBSTR CRowsetBaseImpl::m_strCommandText;
```

## <a name="strindextext"></a> CRowsetImpl::m_strındextext

Satır kümesinin başlangıç dizini içeriyor.

### <a name="syntax"></a>Sözdizimi

```cpp
CComBSTR CRowsetBaseImpl::m_strIndexText;
```