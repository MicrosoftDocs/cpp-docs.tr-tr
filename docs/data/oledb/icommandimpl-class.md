---
description: 'Şu konuda daha fazla bilgi edinin: ıommandimpl sınıfı'
title: ICommandImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ICommandImpl
- ICommandImpl::Cancel
- Cancel
- ICommandImpl.Cancel
- ICommandImpl::CancelExecution
- ATL::ICommandImpl::CancelExecution
- ATL.ICommandImpl.CancelExecution
- CancelExecution
- ICommandImpl.CancelExecution
- ICommandImpl::CreateRowset
- ICommandImpl.CreateRowset
- CreateRowset
- ICommandImpl::Execute
- ICommandImpl.Execute
- ICommandImpl::GetDBSession
- GetDBSession
- ICommandImpl.GetDBSession
- ATL.ICommandImpl.ICommandImpl
- ATL::ICommandImpl::ICommandImpl
- ICommandImpl::ICommandImpl
- ICommandImpl.ICommandImpl
- ICommandImpl::m_bCancel
- ICommandImpl.m_bCancel
- m_bCancel
- ATL::ICommandImpl::m_bCancel
- ATL.ICommandImpl.m_bCancel
- ICommandImpl::m_bCancelWhenExecuting
- ICommandImpl.m_bCancelWhenExecuting
- ATL::ICommandImpl::m_bCancelWhenExecuting
- m_bCancelWhenExecuting
- ATL.ICommandImpl.m_bCancelWhenExecuting
- ICommandImpl.m_bIsExecuting
- ATL::ICommandImpl::m_bIsExecuting
- m_bIsExecuting
- ATL.ICommandImpl.m_bIsExecuting
- ICommandImpl::m_bIsExecuting
helpviewer_keywords:
- ICommandImpl class
- Cancel method
- CancelExecution method
- CreateRowset method
- Execute method
- GetDBSession method
- ICommandImpl constructor
- ICommandImpl class, constructor
- m_bCancel
- m_bCancelWhenExecuting
- m_bIsExecuting
ms.assetid: ef285fef-0d66-45e6-a762-b03357098e3b
ms.openlocfilehash: 62066d689e51a8ca8a71bb8120199c05ed2811d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287391"
---
# <a name="icommandimpl-class"></a>ICommandImpl Sınıfı

[ICommand](/previous-versions/windows/desktop/ms709737(v=vs.85)) arabirimi için uygulama sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, class CommandBase = ICommand>
class ATL_NO_VTABLE ICommandImpl : public CommandBase
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, öğesinden türetilir `ICommandImpl` .

*CommandBase*<br/>
Bir komut arabirimi. Varsayılan değer: `ICommand`.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

| Ad | Açıklama |
|-|-|
|[İptal](#cancel)|Geçerli komut yürütmesini iptal eder.|
|[CancelExecution](#cancelexecution)|Geçerli komut yürütmesini iptal eder.|
|[CreateRowset](#createrowset)|Satır kümesi nesnesi oluşturur.|
|[Yürütme](#execute)|Komutunu yürütür.|
|[GetDBSession](#getdbsession)|Komutu oluşturan oturuma bir arabirim işaretçisi döndürür.|
|[ICommandImpl](#icommandimpl)|Oluşturucu.|

### <a name="data-members"></a>Veri üyeleri

| Ad | Açıklama |
|-|-|
|[m_bCancel](#bcancel)|Komutun iptal edilip edilmeyeceğini gösterir.|
|[m_bCancelWhenExecuting](#bcancelwhenexecuting)|Yürütme sırasında komutun iptal edilip edilmeyeceğini gösterir.|
|[m_bIsExecuting](#bisexecuting)|Komutun Şu anda yürütülmekte olup olmadığını gösterir.|

## <a name="remarks"></a>Açıklamalar

Komut nesnesinde zorunlu arabirim.

## <a name="icommandimplcancel"></a><a name="cancel"></a> Iommandimpl:: Cancel

Geçerli komut yürütmesini iptal eder.

### <a name="syntax"></a>Syntax

```cpp
STDMETHOD(Cancel)();
```

### <a name="remarks"></a>Açıklamalar

*OLE DB Programcı başvurusunda* bkz. [ICommand:: Cancel](/previous-versions/windows/desktop/ms714402(v=vs.85)) .

## <a name="icommandimplcancelexecution"></a><a name="cancelexecution"></a> Iommandimpl:: iptal Lexecution

Geçerli komut yürütmesini iptal eder.

### <a name="syntax"></a>Syntax

```cpp
HRESULT CancelExecution();
```

## <a name="icommandimplcreaterowset"></a><a name="createrowset"></a> Iommandimpl:: CreateRowset

Tek bir satır kümesi oluşturmak için [Execute](#execute) tarafından çağırılır.

### <a name="syntax"></a>Sözdizimi

```cpp
template template <class RowsetClass>
HRESULT CreateRowset(IUnknown* pUnkOuter,
   REFIID riid,
   DBPARAMS* pParams,
   DBROWCOUNT* pcRowsAffected,
   IUnknown** ppRowset,
   RowsetClass*& pRowsetObj);
```

#### <a name="parameters"></a>Parametreler

*RowsetClass*<br/>
Kullanıcının satır kümesi sınıfını temsil eden bir şablon sınıfı üyesi. Genellikle sihirbaz tarafından oluşturulur.

*pUnkOuter*<br/>
'ndaki `IUnknown` Satır kümesi toplama kapsamında oluşturulduysa denetim arabirimine yönelik bir işaretçi; Aksi takdirde, null olur.

*riıd*<br/>
'ndaki İçindeki *riid* öğesine karşılık gelir `ICommand::Execute` .

*pParams*<br/>
[ın/out] İçindeki *pParams* 'e karşılık gelir `ICommand::Execute` .

*etkilenen pcrowsa*<br/>
İçindeki *Pcrowsaöğesine* karşılık gelir `ICommand::Execute` .

*ppRowset*<br/>
[ın/out] İçindeki *ppRowset* öğesine karşılık gelir `ICommand::Execute` .

*pRowsetObj*<br/>
dışı Satır kümesi nesnesi işaretçisi. Genellikle bu parametre kullanılmaz, ancak bir COM nesnesine geçirmeden önce satır kümesinde daha fazla iş gerçekleştirmeniz gerekiyorsa kullanılabilir. *PRowsetObj* ömrü *ppRowset* ile ilişkilidir.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri. `ICommand::Execute`Tipik değerlerin listesi için bkz..

### <a name="remarks"></a>Açıklamalar

Birden fazla satır kümesi oluşturmak veya farklı satır kümeleri oluşturmak için kendi koşullarınızı sağlamak için içinden uygulamasına farklı çağrılar koyun `CreateRowset` `Execute` .

*OLE DB Programcı başvurusunda bkz.* [ICommand:: Execute](/previous-versions/windows/desktop/ms718095(v=vs.85)) .

## <a name="icommandimplexecute"></a><a name="execute"></a> Icommandimpl:: Execute

Komutunu yürütür.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT Execute(IUnknown* pUnkOuter,
   REFIID riid,
   DBPARAMS* pParams,
   DBROWCOUNT* pcRowsAffected,
   IUnknown** ppRowset);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* bkz. [ICommand:: Execute](/previous-versions/windows/desktop/ms718095(v=vs.85)) .

### <a name="remarks"></a>Açıklamalar

İstenen giden arabirim, bu işlevin oluşturduğu satır kümesi nesnesinden alınan bir arabirim olacaktır.

`Execute`[CreateRowset](#createrowset)çağırır. Birden fazla satır kümesi oluşturmak veya farklı satır kümeleri oluşturmak için kendi koşullarınızı sağlamak üzere varsayılan uygulamayı geçersiz kılın.

## <a name="icommandimplgetdbsession"></a><a name="getdbsession"></a> Iommandimpl:: GetDBSession

Komutu oluşturan oturuma bir arabirim işaretçisi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD (GetDBSession) (REFIID riid,
   IUnknown** ppSession);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* bkz. [ICommand:: getdbsession](/previous-versions/windows/desktop/ms719622(v=vs.85)) .

### <a name="remarks"></a>Açıklamalar

Oturumdan özellikleri almak için faydalıdır.

## <a name="icommandimplicommandimpl"></a><a name="icommandimpl"></a> Iommandimpl:: ıommandimpl

Oluşturucu.

### <a name="syntax"></a>Syntax

```cpp
ICommandImpl();
```

## <a name="icommandimplm_bcancel"></a><a name="bcancel"></a> Iommandimpl:: m_bCancel

Komutun iptal edilip edilmeyeceğini gösterir.

### <a name="syntax"></a>Syntax

```cpp
unsigned m_bCancel:1;
```

### <a name="remarks"></a>Açıklamalar

Bu değişkeni `Execute` komut sınıfınızın yönteminde alabilir ve uygun şekilde iptal edebilirsiniz.

## <a name="icommandimplm_bcancelwhenexecuting"></a><a name="bcancelwhenexecuting"></a> Iommandimpl:: m_bCancelWhenExecuting

Yürütme sırasında komutun iptal edilip edilmeyeceğini gösterir.

### <a name="syntax"></a>Syntax

```cpp
unsigned m_bCancelWhenExecuting:1;
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak **`true`** (iptal edilebilir).

## <a name="icommandimplm_bisexecuting"></a><a name="bisexecuting"></a> Iommandimpl:: m_bIsExecuting

Komutun Şu anda yürütülmekte olup olmadığını gösterir.

### <a name="syntax"></a>Syntax

```cpp
unsigned m_bIsExecuting:1;
```

### <a name="remarks"></a>Açıklamalar

`Execute`Komut sınıfınızın yöntemi bu değişkeni olarak ayarlayabilir **`true`** .

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB sağlayıcı şablonu mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)
