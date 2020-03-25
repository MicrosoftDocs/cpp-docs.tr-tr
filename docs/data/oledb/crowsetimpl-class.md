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
ms.openlocfilehash: 97a79dee826dfba4b42053bbeba8c65e4d2b429c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211191"
---
# <a name="crowsetimpl-class"></a>CRowsetImpl Sınıfı

Birçok uygulama arabiriminin birden çok devralınması gerekmeden standart bir OLE DB satır kümesi uygulamasını sağlar.

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

*Şı*<br/>
Kullanıcının `CRowsetImpl`türettiği sınıfı.

*Depolama*<br/>
Kullanıcı kayıt sınıfı.

*CreatorClass*<br/>
Satır kümesi için özellikler içeren sınıf; genellikle komutu.

*ArrayType*<br/>
Satır kümesinin verileri için depolama alanı olarak görev yapacak sınıf. Bu parametrenin varsayılan değeri `CAtlArray`, ancak gerekli işlevselliği destekleyen herhangi bir sınıf olabilir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[Namefromdbıd](#namefromdbid)|Bir `DBID` dize ayıklar ve geçirilen *BSTR* 'ye kopyalar.|
|[SetCommandText](#setcommandtext)|`DBID`s 'yi iki dizinin ([m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) ve [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)) doğrular ve depolar.|

### <a name="overridable-methods"></a>Geçersiz kılınabilir Yöntemler

|||
|-|-|
|[GetColumnInfo](#getcolumninfo)|Belirli bir istemci isteği için sütun bilgilerini alır.|
|[GetCommandFromID](#getcommandfromid)|Her iki parametre de dize değerleri içeriyorsa ve bu durumda dize değerlerini [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) ve [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)veri üyelerine kopyalar.|
|[ValidateCommandID](#validatecommandid)|`DBID`s veya her ikisi de dize değerleri içeriyorsa ve bu durumda bunları veri üyelerine [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) ve [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)kopyalar.|

### <a name="data-members"></a>Veri üyeleri

|||
|-|-|
|[m_rgRowData](#rgrowdata)|Varsayılan olarak, `CRowsetImpl`için Kullanıcı kayıt şablonu bağımsız değişkeninde şablonlaştırılmış bir `CAtlArray`. `ArrayType` şablon bağımsız değişkeni `CRowsetImpl`olarak değiştirilerek başka bir dizi türü sınıfı kullanılabilir.|
|[m_strCommandText](#strcommandtext)|Satır kümesinin ilk komutunu içerir.|
|[m_strIndexText](#strindextext)|Satır kümesinin ilk dizinini içerir.|

## <a name="remarks"></a>Açıklamalar

`CRowsetImpl` statik uplarsa biçiminde geçersiz kılmalar sağlar. Yöntemler, belirli bir satır kümesinin komut metnini ne şekilde doğrulayacağını denetler. Uygulama arabirimlerinizi birden çok devralınmış yaparak kendi `CRowsetImpl`stili sınıfınızı oluşturabilirsiniz. Uygulama sağlamanız gereken tek yöntem `Execute`. Oluşturmakta olduğunuz satır kümesi türüne bağlı olarak, Oluşturucu yöntemleri `Execute`için farklı imzalar bekler. Örneğin, bir şema satır kümesi uygulamak için `CRowsetImpl`türetilmiş bir sınıf kullanıyorsanız, `Execute` yöntemi aşağıdaki imzaya sahip olur:

`HRESULT Execute(LONG* pcRows, ULONG cRestrictions, const VARIANT* rgRestrictions)`

Bir komut veya oturumun satır kümesini uygulamak için `CRowsetImpl`türetilmiş bir sınıf oluşturuyorsanız, `Execute` yöntemi aşağıdaki imzaya sahip olur:

`HRESULT Execute(LONG* pcRows, DBPARAMS* pParams)`

`CRowsetImpl`türetilen `Execute` yöntemlerinden herhangi birini uygulamak için iç veri arabelleklerinizi ([m_rgRowData](../../data/oledb/crowsetimpl-m-rgrowdata.md)) doldurmanız gerekir.

## <a name="crowsetimplnamefromdbid"></a><a name="namefromdbid"></a>CRowsetImpl:: Namefromdbıd

Bir `DBID` dize ayıklar ve geçirilen *BSTR* 'ye kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT CRowsetBaseImpl::NameFromDBID(DBID* pDBID,
   CComBSTR& bstr,
   bool bIndex);
```

#### <a name="parameters"></a>Parametreler

*Pddeklarasyon*<br/>
'ndaki Bir dizenin ayıklanacağı `DBID` işaretçisi.

*BSTR*<br/>
'ndaki `DBID` dizesinin bir kopyasını yerleştirmek için bir [CComBSTR](../../atl/reference/ccombstr-class.md) başvurusu.

*bIndex*<br/>
'ndaki Dizin `DBID`**true ise doğru** Tablo `DBID`**false** .

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT. `DBID` bir tablo veya dizin ( *Bindex*tarafından belirtilen) olmasına bağlı olarak, yöntem DB_E_NOINDEX veya DB_E_NOTABLE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md) ve [Getcommandfromın](../../data/oledb/crowsetimpl-getcommandfromid.md)`CRowsetImpl` uygulamaları tarafından çağrılır.

## <a name="crowsetimplsetcommandtext"></a><a name="setcommandtext"></a>CRowsetImpl:: SetCommandText

`DBID`s 'yi iki dizinin ([m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) ve [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)) doğrular ve depolar.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT CRowsetBaseImpl::SetCommandText(DBID* pTableID,
   DBID* pIndexID);
```

#### <a name="parameters"></a>Parametreler

*PTableID*<br/>
'ndaki Tablo KIMLIĞINI temsil eden `DBID` işaretçisi.

*Pındexıd*<br/>
'ndaki Dizin KIMLIĞINI temsil eden `DBID` işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

`SetCommentText` yöntemi, `IOpenRowsetImpl`statik şablonlaştırılmış bir yöntem olan `CreateRowset`tarafından çağrılır.

Bu yöntem, bir veya daha fazla bir işaretçi aracılığıyla [ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md) ve [Getcommandfromid](../../data/oledb/crowsetimpl-getcommandfromid.md) çağırarak işini devreder.

## <a name="crowsetimplgetcolumninfo"></a><a name="getcolumninfo"></a>CRowsetImpl:: GetColumnInfo

Belirli bir istemci isteği için sütun bilgilerini alır.

### <a name="syntax"></a>Sözdizimi

```cpp
static ATLCOLUMNINFO* CRowsetBaseImpl::GetColumnInfo(T* pv,
   ULONG* pcCols);
```

#### <a name="parameters"></a>Parametreler

*bakın*<br/>
'ndaki Kullanıcının `CRowsetImpl` türetilmiş sınıfına yönelik bir işaretçi.

*pcCols*<br/>
'ndaki Döndürülen sütun sayısına yönelik bir işaretçi (çıkış).

### <a name="return-value"></a>Dönüş Değeri

Statik `ATLCOLUMNINFO` yapısına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gelişmiş bir geçersiz kılma.

Bu yöntem, belirli bir istemci isteği için sütun bilgilerini almak üzere çeşitli temel uygulama sınıfları tarafından çağırılır. Genellikle, bu yöntem `IColumnsInfoImpl`tarafından çağırılır. Bu yöntemi geçersiz kılarsınız, yönteminin bir sürümünü `CRowsetImpl`türetilmiş sınıfınıza yerleştirmeniz gerekir. Yöntemi Şablonsuz bir sınıfa yerleştirilebileceği için, *BD* 'i uygun `CRowsetImpl`türetilmiş sınıfa değiştirmelisiniz.

Aşağıdaki örnekte `GetColumnInfo` kullanımı gösterilmektedir. Bu örnekte, `CMyRowset` `CRowsetImpl`türetilmiş bir sınıftır. Bu sınıfın tüm örnekleri için `GetColumnInfo` geçersiz kılmak için, `CMyRowset` sınıf tanımına aşağıdaki yöntemi koyun:

[!code-cpp[NVC_OLEDB_Provider#1](../../data/oledb/codesnippet/cpp/crowsetimpl-getcolumninfo_1.h)]

## <a name="crowsetimplgetcommandfromid"></a><a name="getcommandfromid"></a>CRowsetImpl:: GetCommandFromID

Her iki parametre de dize değerleri içeriyorsa ve bu durumda dize değerlerini [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) ve [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)veri üyelerine kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT CRowsetBaseImpl::GetCommandFromID(DBID* pTableID,
   DBID* pIndexID);
```

#### <a name="parameters"></a>Parametreler

*PTableID*<br/>
'ndaki Tablo KIMLIĞINI temsil eden `DBID` işaretçisi.

*Pındexıd*<br/>
'ndaki Dizin KIMLIĞINI temsil eden `DBID` işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) ve [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)veri üyelerini doldurmak için `CRowsetImpl` tarafından statik bir yukarı dönüştürme aracılığıyla çağrılır. Varsayılan olarak, bu yöntem parametrelerin dize değerleri içerdiğini veya her ikisini de denetler. Dize değerleri içeriyorsa, bu yöntem dize değerlerini veri üyelerine kopyalar. `CRowsetImpl`türetilmiş sınıfınıza bu imzaya sahip bir yöntem yerleştirerek, yöntemi temel uygulama yerine çağırılır.

## <a name="crowsetimplvalidatecommandid"></a><a name="validatecommandid"></a>CRowsetImpl:: ValidateCommandID

`DBID`s veya her ikisi de dize değerleri içeriyorsa ve bu durumda bunları veri üyelerine [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) ve [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT CRowsetBaseImpl::ValidateCommandID(DBID* pTableID,
   DBID* pIndexID);
```

#### <a name="parameters"></a>Parametreler

*PTableID*<br/>
'ndaki Tablo KIMLIĞINI temsil eden `DBID` işaretçisi.

*Pındexıd*<br/>
'ndaki Dizin KIMLIĞINI temsil eden `DBID` işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [m_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) ve [m_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)veri üyelerini doldurmak için `CRowsetImpl` tarafından statik bir yukarı dönüştürme aracılığıyla çağrılır. Varsayılan olarak, bu yöntem `DBID`s veya her ikisi de dize değerleri içeriyorsa ve bu durumda bunları veri üyelerine kopyalar. `CRowsetImpl`türetilmiş sınıfınıza bu imzaya sahip bir yöntem yerleştirerek, yöntemi temel uygulama yerine çağırılır.

## <a name="crowsetimplm_rgrowdata"></a><a name="rgrowdata"></a>CRowsetImpl:: m_rgRowData

Varsayılan olarak, `CRowsetImpl`için Kullanıcı kayıt şablonu bağımsız değişkeninde şablonlaştırılmış bir `CAtlArray`.

### <a name="syntax"></a>Sözdizimi

```cpp
ArrayType CRowsetBaseImpl::m_rgRowData;
```

### <a name="remarks"></a>Açıklamalar

*ArrayType* `CRowsetImpl`bir şablon parametresidir.

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
