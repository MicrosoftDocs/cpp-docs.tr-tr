---
title: Icommandımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
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
- ICommandImpl
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 91b273e8bfda6c050fa3d9d6db7aafffbe03d684
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50077627"
---
# <a name="icommandimpl-class"></a>ICommandImpl Sınıfı

Uygulamasını sağlar [ICommand](/previous-versions/windows/desktop/ms709737) arabirimi.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, class CommandBase = ICommand>
class ATL_NO_VTABLE ICommandImpl : public CommandBase
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, türetilen `ICommandImpl`.

*CommandBase*<br/>
Bir komut arabirimi. Varsayılan, `ICommand` değeridir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldb.h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[İptal Etme](#cancel)|Geçerli komut yürütme iptal eder.|
|[CancelExecution](#cancelexecution)|Geçerli komut yürütme iptal eder.|
|[CreateRowset](#createrowset)|Bir satır kümesi nesnesi oluşturur.|
|[Execute](#execute)|Komutu yürütür.|
|[GetDBSession](#getdbsession)|Komutu tarafından oluşturulan oturuma bir arabirim işaretçisini döndürür.|
|[Icommandımpl](#icommandimpl)|Oluşturucu.|

### <a name="data-members"></a>Veri üyeleri

|||
|-|-|
|[m_bCancel](#bcancel)|Komut iptal edilebilir olup olmadığını belirtir.|
|[m_bCancelWhenExecuting](#bcancelwhenexecuting)|Komutu yürütürken iptal edilebilir olup olmadığını belirtir.|
|[m_bIsExecuting](#bisexecuting)|Komut yürütülmekte olmadığını gösterir.|

## <a name="remarks"></a>Açıklamalar

Komut nesnesi üzerinde zorunlu bir arabirim.

## <a name="cancel"></a> Icommandımpl::Cancel

Geçerli komut yürütme iptal eder.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(Cancel)();
```

### <a name="remarks"></a>Açıklamalar

Bkz: [ICommand::Cancel](/previous-versions/windows/desktop/ms714402) içinde *OLE DB Programcının Başvurusu*.

## <a name="cancelexecution"></a> Icommandımpl::cancelexecution

Geçerli komut yürütme iptal eder.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT CancelExecution();
```

## <a name="createrowset"></a> Icommandımpl::createrowset

Çağıran [yürütme](../../data/oledb/icommandimpl-execute.md) tek bir satır kümesi oluşturmak için.

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
Kullanıcının satır kümesi sınıfı temsil eden bir şablon sınıfı üyesinin. Genellikle sihirbaz tarafından oluşturulan.

*pUnkOuter*<br/>
[in] Denetlemek için bir işaretçi `IUnknown` bir toplamanın parçası satır kümesi oluşturuluyorsa arabirim; Aksi takdirde null olur.

*riid*<br/>
[in] Karşılık gelen *riid* içinde `ICommand::Execute`.

*pParams*<br/>
[daraltma/genişletme] Karşılık gelen *pParams* içinde `ICommand::Execute`.

*pcRowsAffected*<br/>
Karşılık gelen *pcRowsAffected* içinde `ICommand::Execute`.

*ppRowset*<br/>
[daraltma/genişletme] Karşılık gelen *ppRowset* içinde `ICommand::Execute`.

*pRowsetObj*<br/>
[out] Bir satır kümesi nesnesi işaretçisi. Genellikle bu parametre kullanılmaz, ancak, daha fazla iş satır kümesinde bir COM nesnesine iletmeden önce gerçekleştirmeniz gerekirse kullanılabilir. Ömrünü *pRowsetObj* bağlı olan *ppRowset*.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini. Bkz: `ICommand::Execute` genel değerler listesi.

### <a name="remarks"></a>Açıklamalar

Birden fazla satır kümesi oluşturmak için ya da farklı satır kümeleri oluşturmak için kendi koşulları sağlamak için farklı çağrıları yerleştirin `CreateRowset` içinden `Execute`.

Bkz: [ICommand::Execute](/previous-versions/windows/desktop/ms718095) içinde *OLE DB Programcının Başvurusu.*

## <a name="execute"></a> Icommandımpl::Execute

Komutu yürütür.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT Execute(IUnknown* pUnkOuter,
   REFIID riid,
   DBPARAMS* pParams,
   DBROWCOUNT* pcRowsAffected,
   IUnknown** ppRowset);
```

#### <a name="parameters"></a>Parametreler

Bkz: [ICommand::Execute](/previous-versions/windows/desktop/ms718095) içinde *OLE DB Programcının Başvurusu*.

### <a name="remarks"></a>Açıklamalar

İstenen giden arabirimi bu işlevi oluşturan satır kümesi nesnesinden alınan bir arabirim olacaktır.

`Execute` çağrıları [CreateRowset](../../data/oledb/icommandimpl-createrowset.md). Varsayılan uygulama birden fazla satır kümesi oluşturun veya farklı satır kümeleri oluşturmak için kendi koşulları sağlamak için geçersiz kılın.

## <a name="getdbsession"></a> Icommandımpl::getdbsession

Komutu tarafından oluşturulan oturuma bir arabirim işaretçisini döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD (GetDBSession) (REFIID riid,
   IUnknown** ppSession);
```

#### <a name="parameters"></a>Parametreler

Bkz: [ICommand::GetDBSession](/previous-versions/windows/desktop/ms719622) içinde *OLE DB Programcının Başvurusu*.

### <a name="remarks"></a>Açıklamalar

Oturumdan özellikleri almak için yararlıdır.

## <a name="icommandimpl"></a> Icommandımpl::ıcommandımpl

Oluşturucu.

### <a name="syntax"></a>Sözdizimi

```cpp
ICommandImpl();
```

## <a name="bcancel"></a> Icommandımpl::m_bcancel

Komut iptal olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
unsigned m_bCancel:1;
```

### <a name="remarks"></a>Açıklamalar

Bu değişkeni, alabilirsiniz `Execute` komut sınıfı ve uygun şekilde iptal yöntemi.

## <a name="bcancelwhenexecuting"></a> Icommandımpl::m_bcancelwhenexecuting

Komutu yürütürken iptal edilebilir olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
unsigned m_bCancelWhenExecuting:1;
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak **true** (iptal edilebilir).

## <a name="bisexecuting"></a> Icommandımpl::m_bısexecuting

Komut yürütülmekte olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
unsigned m_bIsExecuting:1;
```

### <a name="remarks"></a>Açıklamalar

`Execute` Komutu sınıfınızın yöntemi bu değişkeni ayarlayabilirsiniz **true**.

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)