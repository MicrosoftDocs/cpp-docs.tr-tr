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
ms.openlocfilehash: 35a80503597b7e59ec10618b9c8e18e0e69f018e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221516"
---
# <a name="crowsetimpl-class"></a>CRowsetImpl Sınıfı

Birçok uygulama arabiriminin birden çok devralınması gerekmeden standart bir OLE DB satır kümesi uygulamasını sağlar.

## <a name="syntax"></a>Söz dizimi

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
Kullanıcının sınıfından türetilen sınıfı `CRowsetImpl` .

*Depolama*<br/>
Kullanıcı kayıt sınıfı.

*CreatorClass*<br/>
Satır kümesi için özellikler içeren sınıf; genellikle komutu.

*ArrayType*<br/>
Satır kümesinin verileri için depolama alanı olarak görev yapacak sınıf. Bu parametre varsayılan olarak olur `CAtlArray` , ancak gerekli işlevselliği destekleyen herhangi bir sınıf olabilir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[Namefromdbıd](#namefromdbid)|Bir dizeden bir dize ayıklar `DBID` ve geçirilen *BSTR* 'e kopyalar.|
|[SetCommandText](#setcommandtext)|, `DBID` S 'yi iki dizelerdeki ([m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) ve [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)) doğrular ve depolar.|

### <a name="overridable-methods"></a>Geçersiz kılınabilir Yöntemler

|||
|-|-|
|[GetColumnInfo](#getcolumninfo)|Belirli bir istemci isteği için sütun bilgilerini alır.|
|[GetCommandFromID](#getcommandfromid)|Her iki parametre de dize değerleri içeriyorsa ve bu durumda dize değerlerini [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) ve [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)veri üyelerine kopyalar.|
|[ValidateCommandID](#validatecommandid)|Her birinin veya her ikisinin de `DBID` dize değerleri içerdiğini ve bu durumda, [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) ve [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)veri üyelerine kopyalar.|

### <a name="data-members"></a>Veri üyeleri

|||
|-|-|
|[m_rgRowData](#rgrowdata)|Varsayılan olarak, `CAtlArray` Kullanıcı kayıt şablonu bağımsız değişkeninde templatıka `CRowsetImpl` . Şablon bağımsız değişkeni olarak değiştirilerek, başka bir dizi türü sınıfı kullanılabilir `ArrayType` `CRowsetImpl` .|
|[m_strCommandText](#strcommandtext)|Satır kümesinin ilk komutunu içerir.|
|[m_strIndexText](#strindextext)|Satır kümesinin ilk dizinini içerir.|

## <a name="remarks"></a>Açıklamalar

`CRowsetImpl`statik uplarsa biçiminde geçersiz kılmalar sağlar. Yöntemler, belirli bir satır kümesinin komut metnini ne şekilde doğrulayacağını denetler. `CRowsetImpl`Uygulama arabirimlerinizi birden çok devralınmış yaparak kendi stil sınıfınızı oluşturabilirsiniz. Uygulama sağlamanız gereken tek yöntem `Execute` . Oluşturmakta olduğunuz satır kümesi türüne bağlı olarak, Oluşturucu yöntemleri için farklı imzalar bekler `Execute` . Örneğin, bir `CRowsetImpl` şema satır kümesi uygulamak için bir türetilmiş sınıf kullanıyorsanız, `Execute` yöntemi aşağıdaki imzaya sahip olur:

`HRESULT Execute(LONG* pcRows, ULONG cRestrictions, const VARIANT* rgRestrictions)`

Bir `CRowsetImpl` komut veya oturumun satır kümesini uygulamak için bir türetilmiş sınıf oluşturuyorsanız, `Execute` yöntemi aşağıdaki imzaya sahip olur:

`HRESULT Execute(LONG* pcRows, DBPARAMS* pParams)`

Türetilmiş yöntemlerden herhangi birini uygulamak için `CRowsetImpl` `Execute` iç veri arabelleklerinizi ([m_rgRowData](../../data/oledb/crowsetimpl-m-rgrowdata.md)) doldurmanız gerekir.

## <a name="crowsetimplnamefromdbid"></a><a name="namefromdbid"></a>CRowsetImpl:: Namefromdbıd

Bir dizeden bir dize ayıklar `DBID` ve geçirilen *BSTR* 'e kopyalar.

### <a name="syntax"></a>Söz dizimi

```cpp
HRESULT CRowsetBaseImpl::NameFromDBID(DBID* pDBID,
   CComBSTR& bstr,
   bool bIndex);
```

#### <a name="parameters"></a>Parametreler

*Pddeklarasyon*<br/>
'ndaki Bir `DBID` dizenin ayıklanacağı bir işaretçisi.

*bstr*<br/>
'ndaki Dizenin bir kopyasını yerleştirmek için bir [CComBSTR](../../atl/reference/ccombstr-class.md) başvurusu `DBID` .

*bIndex*<br/>
[in] **`true`** Eğer bir dizin ise, `DBID` **`false`** bir tablo `DBID` .

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT. `DBID`Bir tablo veya dizin olmasına bağlı olarak ( *bindex*tarafından belirtilen), yöntem DB_E_NOINDEX veya DB_E_NOTABLE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CRowsetImpl` [ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md) ve [getcommandfromin](../../data/oledb/crowsetimpl-getcommandfromid.md)uygulamaları tarafından çağırılır.

## <a name="crowsetimplsetcommandtext"></a><a name="setcommandtext"></a>CRowsetImpl:: SetCommandText

, `DBID` S 'yi iki dizelerdeki ([m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) ve [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)) doğrular ve depolar.

### <a name="syntax"></a>Söz dizimi

```cpp
HRESULT CRowsetBaseImpl::SetCommandText(DBID* pTableID,
   DBID* pIndexID);
```

#### <a name="parameters"></a>Parametreler

*PTableID*<br/>
'ndaki `DBID`Tablo kimliğini temsil eden bir işaretçisi.

*Pındexıd*<br/>
'ndaki `DBID`DIZIN kimliğini temsil eden bir işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

`SetCommentText`Yöntemi `CreateRowset` , bir statik şablonlaştırılmış yöntemi tarafından çağrılır `IOpenRowsetImpl` .

Bu yöntem, bir veya daha fazla bir işaretçi aracılığıyla [ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md) ve [Getcommandfromid](../../data/oledb/crowsetimpl-getcommandfromid.md) çağırarak işini devreder.

## <a name="crowsetimplgetcolumninfo"></a><a name="getcolumninfo"></a>CRowsetImpl:: GetColumnInfo

Belirli bir istemci isteği için sütun bilgilerini alır.

### <a name="syntax"></a>Söz dizimi

```cpp
static ATLCOLUMNINFO* CRowsetBaseImpl::GetColumnInfo(T* pv,
   ULONG* pcCols);
```

#### <a name="parameters"></a>Parametreler

*bakın*<br/>
'ndaki Kullanıcının türetilmiş sınıfına yönelik bir işaretçi `CRowsetImpl` .

*pcCols*<br/>
'ndaki Döndürülen sütun sayısına yönelik bir işaretçi (çıkış).

### <a name="return-value"></a>Dönüş Değeri

Statik `ATLCOLUMNINFO` Yapı işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gelişmiş bir geçersiz kılma.

Bu yöntem, belirli bir istemci isteği için sütun bilgilerini almak üzere çeşitli temel uygulama sınıfları tarafından çağırılır. Genellikle, bu yöntem tarafından çağırılır `IColumnsInfoImpl` . Bu yöntemi geçersiz kılarsınız, yöntemin bir sürümünü `CRowsetImpl` türetilmiş sınıfınıza yerleştirmeniz gerekir. Yöntemi Şablonsuz bir sınıfa yerleştirilebileceği için, *BD* 'i uygun `CRowsetImpl` türetilmiş sınıfa değiştirmelisiniz.

Aşağıdaki örnekte kullanım gösterilmektedir `GetColumnInfo` . Bu örnekte, `CMyRowset` bir `CRowsetImpl` türetilmiş sınıftır. `GetColumnInfo`Bu sınıfın tüm örnekleri için geçersiz kılmak üzere, sınıf tanımına aşağıdaki yöntemi koyun `CMyRowset` :

[!code-cpp[NVC_OLEDB_Provider#1](../../data/oledb/codesnippet/cpp/crowsetimpl-getcolumninfo_1.h)]

## <a name="crowsetimplgetcommandfromid"></a><a name="getcommandfromid"></a>CRowsetImpl:: GetCommandFromID

Her iki parametre de dize değerleri içeriyorsa ve bu durumda dize değerlerini [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) ve [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)veri üyelerine kopyalar.

### <a name="syntax"></a>Söz dizimi

```cpp
HRESULT CRowsetBaseImpl::GetCommandFromID(DBID* pTableID,
   DBID* pIndexID);
```

#### <a name="parameters"></a>Parametreler

*PTableID*<br/>
'ndaki `DBID`Tablo kimliğini temsil eden bir işaretçisi.

*Pındexıd*<br/>
'ndaki `DBID`DIZIN kimliğini temsil eden bir işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

Bu yöntem `CRowsetImpl` , [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) ve [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)veri üyelerini doldurmak için tarafından statik bir upcast aracılığıyla çağrılır. Varsayılan olarak, bu yöntem parametrelerin dize değerleri içerdiğini veya her ikisini de denetler. Dize değerleri içeriyorsa, bu yöntem dize değerlerini veri üyelerine kopyalar. Türetilmiş sınıfınıza bu imzaya sahip bir yöntem yerleştirerek `CRowsetImpl` , yöntemi temel uygulama yerine çağırılır.

## <a name="crowsetimplvalidatecommandid"></a><a name="validatecommandid"></a>CRowsetImpl:: ValidateCommandID

Her birinin veya her ikisinin de `DBID` dize değerleri içerdiğini ve bu durumda, [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) ve [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)veri üyelerine kopyalar.

### <a name="syntax"></a>Söz dizimi

```cpp
HRESULT CRowsetBaseImpl::ValidateCommandID(DBID* pTableID,
   DBID* pIndexID);
```

#### <a name="parameters"></a>Parametreler

*PTableID*<br/>
'ndaki `DBID`Tablo kimliğini temsil eden bir işaretçisi.

*Pındexıd*<br/>
'ndaki `DBID`DIZIN kimliğini temsil eden bir işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CRowsetImpl` [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) ve [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)veri üyelerini doldurmak için tarafından statik bir upcast aracılığıyla çağrılır. Bu yöntem, varsayılan olarak, her birinin veya her ikisinin de `DBID` dize değerleri içerdiğini veya varsa, bunları kendi veri üyelerine kopyayor olup olmadığını denetler. Türetilmiş sınıfınıza bu imzaya sahip bir yöntem yerleştirerek `CRowsetImpl` , yöntemi temel uygulama yerine çağırılır.

## <a name="crowsetimplm_rgrowdata"></a><a name="rgrowdata"></a>CRowsetImpl:: m_rgRowData

Varsayılan olarak, `CAtlArray` Kullanıcı kayıt şablonu bağımsız değişkeninde templatıka `CRowsetImpl` .

### <a name="syntax"></a>Sözdizimi

```cpp
ArrayType CRowsetBaseImpl::m_rgRowData;
```

### <a name="remarks"></a>Açıklamalar

*ArrayType* , için bir şablon parametresidir `CRowsetImpl` .

## <a name="crowsetimplm_strcommandtext"></a><a name="strcommandtext"></a>CRowsetImpl:: m_strCommandText

Satır kümesinin ilk komutunu içerir.

### <a name="syntax"></a>Sözdizimi

```cpp
CComBSTR CRowsetBaseImpl::m_strCommandText;
```

## <a name="crowsetimplm_strindextext"></a><a name="strindextext"></a>CRowsetImpl:: m_strIndexText

Satır kümesinin ilk dizinini içerir.

### <a name="syntax"></a>Sözdizimi

```cpp
CComBSTR CRowsetBaseImpl::m_strIndexText;
```
